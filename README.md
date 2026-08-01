# Knowledge Representation

## Introduction

Drawing inspiration from previous general-purpose knowledge-representation formats including [XML](https://en.wikipedia.org/wiki/XML), [HTML](https://en.wikipedia.org/wiki/HTML), [RDF](https://en.wikipedia.org/wiki/Resource_Description_Framework), [XUL](https://en.wikipedia.org/wiki/XUL), [XAML](https://en.wikipedia.org/wiki/Extensible_Application_Markup_Language), and [XOML](https://en.wikipedia.org/wiki/Extensible_Application_Markup_Language), this repository is a staging area for innovation, discussion, and building consensus towards advancing existing knowledge-representation formats and proposing new such formats.

## Quick Examples

Expanding on some XAML/XOML concepts, envisioning a related knowledge-representation technology which uses [JavaScript](https://en.wikipedia.org/wiki/JavaScript) for code-behind features while interoperable with [Web Components](https://en.wikipedia.org/wiki/Web_Components), the [Shadow DOM](https://en.wikipedia.org/wiki/Shadow_DOM), and [WebAssembly](https://en.wikipedia.org/wiki/WebAssembly), the following quick examples showcase a number of markup-related possibilities.

```xml
<resource xmlns="http://tbd.org/2026/next" xmlns:x="http://tbd.org/2026/next">
  <head>
    <script src="shapes.js" />
    <script src="brushes.js" />
  </head>
  <body>
    <rectangle width="100" height="100" xmlns="using:rectangle" x:class="rectangle">
      <fill x:attribute="true">
        <solidcolorbrush color="blue" xmlns="using:solidcolorbrush" x:class="solidcolorbrush" />
      </fill>
    </rectangle>
  </body>
</resource>
```

```xml
<rectangle width="100" height="100" xmlns:x="http://tbd.org/2026/next" xmlns="using:rectangle">
  <x:class x:attribute="true" x:type="text/javascript" x:select="rectangle" x:src="shapes.js" />
  <fill x:attribute="true">
    <imgbrush xmlns="using:imgbrush">
      <x:class x:attribute="true" x:type="text/javascript" x:select="imgbrush" x:src="brushes.js" />
      <src x:attribute="true" x:type="multipart/alternative">
        <x:multipart>
          <x:part x:type="image/png" x:src="file.png" />
          <x:part x:type="image/jpeg" x:src="file.jpeg" />
        </x:multipart>
      </src>
    </imgbrush>
  </fill>
  <content x:attribute="true">
    <x:value x:attribute="true" x:type="multipart/alternative">
      <x:multipart>
        <x:part x:lang="en" x:type="text/plain">Hello</x:part>
        <x:part x:lang="fr" x:type="text/plain">Bonjour</x:part>
      </x:multipart>
    </x:value>
  </content>
</rectangle>
```

Above, the `x:attribute` attribute signals that a child element is an _extended attribute_ of its parent element. While simple attributes allow only text-string values, extended attributes allow markup and other content to be used for attributes' values. Extended attributes would present opportunities for expanding on [object models](https://en.wikipedia.org/wiki/Document_Object_Model).

## Representing Workflows

The following example sketch intends to show that one could readily represent workflows using markup supporting extended attributes and an expressiveness for inline JavaScript.

```xml
<sequence xmlns="using:sequence" xmlns:x="http://tbd.org/2026/next">
  <x:class x:attribute="true" x:select="sequence" x:src="workflow.js" />
  <code x:name="start-activity" xmlns="using:code">
    <x:class x:attribute="true" x:select="code" x:src="workflow.js" />
    <execute x:attribute="true" x:type="text/javascript" x:select="onStart">
      <![CDATA[
         function onStart(ctx)
         {
            ...
         }
      ]]>
    </execute>
  </code>
  <code x:name="process-activity" xmlns="using:code">
    <x:class x:attribute="true" x:select="code" x:src="workflow.js" />
    <execute x:attribute="true" x:select="onProcess" x:src="custom.js" />
  </code>
  <code x:name="end-activity" execute="javascript:onEnd" xmlns="using:code">
    <x:class x:attribute="true" x:select="code" x:src="workflow.js" />
  </code>
</sequence>
```

## XML Inclusions

Using [XML inclusions](https://en.wikipedia.org/wiki/XInclude), repeated patterns in markup could be succinctly replaced by `<xi:include>` elements which are processed and subsequently replaced by the content that they reference. More coming soon.

## Parameterized Templates

More coming soon.
