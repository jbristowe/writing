"Blasphemy!"

This is the typical reaction from hardcore XAML enthusiasts when they're told that [Xamarin.Forms](https://www.xamarin.com/forms) XAML can now be styled with [CSS](https://www.w3.org/Style/CSS/Overview.en.html). Yes, we're talking good old Cascading StyleSheets (CSS). Meant for web, but now able to be used to style native cross-platform Xamarin.Forms apps. Sure, it sounds a little weird at first. But it's important to consider that CSS styling for XAML has some unique advantages. This article explores the promise of styling Xamarin.Forms apps with CSS and what lies ahead. This is a new optional way to style your Xamarin.Forms XAML visual elements, where there's not much to lose and plenty to gain!

## Why CSS?

First up, if you are a hater of any web technologies, you need to give up the fight against bringing CSS support to Xamarin.Forms. It is happening. And although it's not in a stable Xamarin.Forms release yet, the [pull request was merged into master in late 2017](https://github.com/xamarin/Xamarin.Forms/pull/1207). The CSS parser is essentially a mapping back to [XAML styles](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/styles/introduction) in use within Xamarin.Forms.

So, why would Microsoft even try to bring CSS goodness from the web world over to Xamarin.Forms? Turns out, there are some real advantages to being able to style native Xamarin.Forms apps with the ease that CSS provides. Here's an informal run down:

### CSS Benefits

Here are a few benefits that CSS provides for styling Xamarin.Forms:

- Essentially, both HTML for web and XAML for Xamarin.Forms build visual trees
- Many Xamarin developers come from an ASP.NET background
- CSS is powerful and well-loved by many
- Developers get to reuse skills they already have from building web apps
- There is a rich ecosystem of extensions and tooling around CSS
- Compared to XAML styling, CSS can be leaner and less verbose
- CSS is essentially providing a mapping back to underlying XAML styles
- All of inline XAML markup for styling can be moved to CSS files
- CSS offers some unique advantages with styling inheritance
- CSS offers the potential of code sharing of styles between web and Xamarin.Forms app
- CSS pre-processing and style templates are supported
- With [Mono's WebAssembly support](http://www.mono-project.com/news/2017/08/09/hello-webassembly/), XAML styling through CSS opens new doors
- CSS use is optional and developers don't complain about flexibility

### Some Caveats

While the promise of CSS styling and code sharing can be enticing, it is important to remember that these are still early days. These are some things to keep in mind:

- XAML styling is the first class citizen in Xamarin.Forms
- CSS plays a side role in providing a familiar approach to styling XAML elements
- One cannot do everything in CSS that is doable in XAML styling
- Some CSS features are not supported, like `[attribute^="value"]` and `@media`
- For now, stylesheets are parsed and evaluated at runtime; they are not compiled
- There is small performance hit as CSS is parsed and mapped back to XAML styles
- CSS styling support isn't official in Xamarin.Forms yet

### The Basics

Time to see how this works. So, how would you go about adding CSS support to your Xamarin.Forms apps? First, you must switch to a Beta release of the Xamarin.Forms NuGet package to utilize CSS. These releases are available by checking the box to see pre-release packages. Anything *2.6.0* onward should work - latest being *3.0.0 Pre 3*. Make this switch in your new or existing Xamarin.Forms project - in .NET Standard/PCL library as well as any platform-specific projects.

![](https://i.imgur.com/27ItkVD.png)

Next up, let's add a generic CSS file - this can live in a */Styles* folder if you foresee the need to keep all your styles organized. 

![](https://i.imgur.com/TjKMJYV.png)

Just make sure to mark the CSS file as an *embedded resource* - this way it is included for parsing in all platform-specific app packages.

![](https://i.imgur.com/Hx2vL9l.png)

That's it! We are now ready to refer to the CSS in our XAML. Simply create a `Resource` for your `ContentPage` and point to the CSS file in your directory.

```xml
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:StylingWithCSS"
             x:Class="StylingWithCSS.StylingWithCSSPage">
  <ContentPage.Resources>
    <StyleSheet Source="MyStyle.css" />
  </ContentPage.Resources>
  <!-- ... -->
</ContentPage>
```
	
You may also load up the CSS as an embedded resource from C# code, but XAML is the more preferred and natural place to tie in CSS. Now, over in our CSS file, let's write the first bit of code to style our XAML visual tree, like so:

```css
^ContentPage {
  background-color: lightgreen;
  padding: 20
}
```
	
The caret symbol (`^`) selects all elements with `ContentPage` as base class, including `ContentPage` itself. While the rest of CSS styling is the same as what you do for web, this is the only selector that isn't part of CSS specifications - this is special for Xamarin.Forms only. Have trust and run your app - you'll see that without changing anything in the default Xamarin.Forms template, we have CSS styling our `ContentPage`. One small line of code, one giant leap in code-sharing prospects!

![](https://i.imgur.com/WId4QQb.png)

Now the CSS file(s) in your Xamarin.Forms projects can be worked on any how you prefer - both Visual Studio for Windows and Mac will offer good support with IntelliSense. You are also free to use your beloved CSS tool. Except for the caret symbol (`^`), it should be business as usual.

## CSS Authenticity

While the promise of being able to style Xamarin.Forms UI with CSS may be exciting, you may have that nagging feeling in your gut: "Is this really CSS? Like, really what we use for HTML?" Yep, this is CSS in all its glory and most its features simply work.

### Element Property Support

One of the immediate benefits is the extensive support for visual element properties. CSS can reach just about any styling property for XAML elements. Here are some most common styling properties familiar to XAML developers:

- `color`
- `background-color`
- `font-family`
- `font-size`
- `font-style`
- `height`
- `width`
- `border-color`
- `border-width`
- `visibility`
- `opacity`
- `text-align`
- `margin` - `left` | `right` | `top` | `bottom`
- `padding` - `left` | `right` | `top` | `bottom`

CSS selectors dictate which elements to act on and these property values can be set just how you would set them from XAML. For precedence, styles with matching selectors are applied, one by one, in definition order. Styles defined on the visual element itself are always applied last. Speaking of selectors, let's take a look at some standard fare to choose XAML visual elements - CSS really shines in flexibility here.

### Style Classes

As you expect, you can assign a CSS *style class* to XAML elements and define the style in your CSS file - in case of property value conflicts, the last style wins. Assume the following XAML:

```xml
<Label Text="Welcome to Xamarin Forms!" StyleClass="MyLabel" />
```

The `Label` has the `.MyLabel` class applied, which is as follows:

```css
.MyLabel {
  color: red;
}
```

Here's how it looks at runtime:

![](https://i.imgur.com/YBbxWfd.png)

### Named Styling

You can refer to any XAML visual element by their generic name as CSS selectors, but you may also fall back to `x:Name` to identify individual elements out of the visual tree. For example, assume the following XAML:

```xml
<Label x:Name="NamedLabel" Text="Hello World" />
```

You can map this `Label` using its `Name` property through an ID selector in CSS:

```css
#NamedLabel {
  font-size: large;
}
```

Here's how it looks at runtime:

![](https://i.imgur.com/2SfP8jV.png)

### Inline Styling

If you have any complex styling needs, you are almost always advised to have your styles defined in a separate CSS file - XAML visual tree definition and its styling can be pulled together at runtime. For very simple scenarios however, you have the option of defining your CSS styles inline within your XAML file:

```xml
<ContentPage.Resources>
  <StyleSheet>
    <![CDATA[
      ^contentpage {
        background-color: aqua;
      }
    ]]>
  </StyleSheet>
</ContentPage.Resources>
```

Here's how it looks at runtime:

![](https://i.imgur.com/xJnUYNT.png)

### Inheritance

Let's get to the cascading part of CSS styling. This is where CSS shines with easy "trickle-down" effects. Assume you want all `Labels` within a `StackLayout` to have a certain style. You can refer to direct children using the `element>element` selector.

Assume the following XAML:

```xml
<StackLayout x:Name="MyStack"
             Orientation="Vertical"
             VerticalOptions="Center"
             HorizontalOptions="Center">
  <Label Text="Welcome to Xamarin Forms!" StyleClass="MyLabel" /> 
  <Label x:Name="NamedLabel" Text="Hello World" />
</StackLayout>
```

Let's style the direct children of the `StackLayout` using the `element>element` selector:

```css
stacklayout>label {
  color: blue;
}
```

You can start to appreciate the power and flexibility that CSS support in Xamarin.Forms provides:

![](https://i.imgur.com/QID69QP.png)

Now, what if you wanted all child elements to have a specific style, even though they do not inherit from a direct parent? Simply use the `element element` selector! Again, let's assume some XAML:

```xml
<StackLayout x:Name="MyStack"
             Orientation="Vertical"
             VerticalOptions="Center"
             HorizontalOptions="Center">
  <Label Text="Welcome to Xamarin Forms!" StyleClass="MyLabel" /> 
  <Label x:Name="NamedLabel" Text="Hello World" />
  <StackLayout Orientation="Vertical">
    <Button Text="Hi" />
  </StackLayout>
</StackLayout>
```

Let's use the `element element` selector to style the button:

```css
stacklayout button {
  background-color: wheat;
}
```

Easy, right?

![](https://i.imgur.com/BUjchsd.png)

## Road Ahead

You may call it a bold outlier move, but CSS styling for Xamarin.Forms is here to stay. CSS brings to the table the ability to style XAML in a less verbose and more efficient way. And the biggest advantage is code sharing between your web and Xamarin.Forms apps.

It doesn't take a mind reader to guess your next set of questions. Now that we have CSS, could we take things to an advanced level and really reap the benefits? Could I be using CSS pre-processors like [Sass](http://sass-lang.com/) and [Less](http://lesscss.org/) in Xamarin.Forms styling and get productivity benefits? If I have a XAML style template, could I use CSS to modify it? I'm using [Telerik UI for Xamarin](https://www.telerik.com/xamarin-ui) for polished performant UI - could I style them with CSS or modify the [built-in theme](https://docs.telerik.com/devtools/xamarin/styling-and-appearance/xamarin-forms-theming/themes-overview)? The answer to all your questions is an emphatic YES! But for the risk of running TL;DR, we'll save this discussion for another article. Until then, stay classy and style your Xamarin.Forms apps just the way you like. Cheers!
