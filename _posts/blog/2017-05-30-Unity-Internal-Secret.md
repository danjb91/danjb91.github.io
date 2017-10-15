---
layout: post
title: Unity Internal Cheat Code
excerpt: "Who knew Unity had cheat codes?"
categories: blog
tags: [CSharp, Unity3d]
comments: false
share: true
author: dan_bradshaw
published: false
---

One of the best tools for writing Unity Editor scripts, is being able to learn directly from the Awesome Team that creates the tools you use every day in the editor. Because the Unity Editor is largely written in C#, this means we can decompile the editor code, and directly see how they are using their APIs, or how they do they fancy things they do!

This used to be quite the controversial topic, but recently Unity have explicitly allowed this in their terms of service. Personally, I use the brilliant application dotPeek from JetBeans. We can select any class in either the UnityEngine, or UnityEditor DLL files and view the decompiled code for the functions in that class. You might quickly notice that some functions don't have decompiled code available, these functions are implemented directly in the C++ part of the engine. This is usually done for optimisation reasons, the code relies on a middleware the engine is using, or (like the render pipeline) they've not got around to exposing implementing it in C#.

<figure>
	<img src="{{ site.url }}/images/articles/dotPeek.png" alt="image">
	<figcaption><a href="{{ site.url }}/images/articles/dotPeek.png" title="You can import the whole Managed Unity folder and find dependancies across the many dll files.">You can import the whole Managed Unity folder and find dependancies across the many dll files.</a></figcaption>
</figure>
While looking at how the Animator window is implemented for a project I'll be talking about soon, I noticed an interesting snippet of code in the **About Unity** window implementation.

```csharp
private void ListenForSecretCodes()
{
	if (Event.current.type != EventType.KeyDown || (int) Event.current.character == 0 || !this.SecretCodeHasBeenTyped("internal", ref this.m_InternalCodeProgress))
		return;
	bool flag = !EditorPrefs.GetBool("InternalMode", false);
	EditorPrefs.SetBool("InternalMode", flag);
	this.ShowNotification(new GUIContent("Internal Mode " + (!flag ? "Off" : "On")));
	InternalEditorUtility.RequestScriptReload();
}
```

Once you've typed *internal* into the **About Unity** window you'll see a notification like below and Unity will recompile the script assemblies.

<figure>
	<a href="{{ site.url }}/images/articles/internal_mode.png"><img src="{{ site.url }}/images/articles/internal_mode.png" alt="image"></a>
</figure>

Now, we can't directly see what this will affect from this area of the decompiled code, but a bit of digging reveales a few bits of code which check this "InternalMode" Editor Preference flag.

Below is just about everything you'll need to style in the theme. Check the source code to see the many embedded elements within paragraphs.

# Heading 1

## Heading 2

### Heading 3

#### Heading 4

##### Heading 5

###### Heading 6

### Body text

Lorem ipsum dolor sit amet, test link adipiscing elit. **This is strong**. Nullam dignissim convallis est. Quisque aliquam.

![Smithsonian Image]({{ site.url }}/images/3953273590_704e3899d5_m.jpg)
{: .pull-right}

*This is emphasized*. Donec faucibus. Nunc iaculis suscipit dui. 53 = 125. Water is H<sub>2</sub>O. Nam sit amet sem. Aliquam libero nisi, imperdiet at, tincidunt nec, gravida vehicula, nisl. The New York Times <cite>(That’s a citation)</cite>. <u>Underline</u>. Maecenas ornare tortor. Donec sed tellus eget sapien fringilla nonummy. Mauris a ante. Suspendisse quam sem, consequat at, commodo vitae, feugiat in, nunc. Morbi imperdiet augue quis tellus.

HTML and <abbr title="cascading stylesheets">CSS<abbr> are our tools. Mauris a ante. Suspendisse quam sem, consequat at, commodo vitae, feugiat in, nunc. Morbi imperdiet augue quis tellus. Praesent mattis, massa quis luctus fermentum, turpis mi volutpat justo, eu volutpat enim diam eget metus.

### Blockquotes

> Lorem ipsum dolor sit amet, test link adipiscing elit. Nullam dignissim convallis est. Quisque aliquam.

## List Types

### Ordered Lists

1. Item one
   1. sub item one
   2. sub item two
   3. sub item three
2. Item two

### Unordered Lists

* Item one
* Item two
* Item three

## Tables

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|----
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=====
| Foot1   | Foot2   | Foot3   |
{: .table}

## Code Snippets

Syntax highlighting via Rouge

```css
#container {
  float: left;
  margin: 0 -240px 0 0;
  width: 100%;
}
```

```csharp
public class test : MonoBehaviour
{
  public static void Test()
  {
    Debug.Log("Test");
  }
}
```

Non Rouge code example

    <div id="awesome">
        <p>This is great isn't it?</p>
    </div>

## Buttons

Make any link standout more when applying the `.btn` class.

<div markdown="0"><a href="#" class="btn">This is a button</a></div>
