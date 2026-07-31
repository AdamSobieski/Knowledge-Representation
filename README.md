# Knowledge Representation

## Introduction

Drawing inspiration from previous general-purpose knowledge-representation formats including [XML](https://en.wikipedia.org/wiki/XML), [HTML](https://en.wikipedia.org/wiki/HTML), [RDF](https://en.wikipedia.org/wiki/Resource_Description_Framework), [XUL](https://en.wikipedia.org/wiki/XUL), [XAML](https://en.wikipedia.org/wiki/Extensible_Application_Markup_Language), and [XOML](https://en.wikipedia.org/wiki/Extensible_Application_Markup_Language), this repository intends to serve as a forum for innovation and building consensus towards advancing existing knowledge-representation formats and/or proposing new such formats.

## A Quick Example

For a quick example, expanding on some XUL/XAML/XOML concepts, envisioning a related technology which binds to JavaScript while interoperable with the [Shadow DOM](https://en.wikipedia.org/wiki/Shadow_DOM) and [WebAssembly](https://en.wikipedia.org/wiki/WebAssembly):

```xml
<rectangle width="100" height="100" xmlns:next="http://tbd.org/2026/next" xmlns="using:rectangle">
  <next:class next:attribute="true" next:type="text/javascript" next:select="rectangle" next:src="shapes.js" />
  <fill next:attribute="true">
    <imagebrush xmlns="using:imagebrush">
      <next:class next:attribute="true" next:type="text/javascript" next:select="imagebrush" next:src="brushes.js" />
      <src next:attribute="true" next:type="multipart/alternative">
        <next:multipart>
          <next:part next:type="image/png" next:src="file.png" />
          <next:part next:type="image/jpeg" next:src="file.jpeg" />
        </next:multipart>
      </src>
    </imagebrush>
  </fill>
  <content next:attribute="true">
    <next:value next:attribute="true" next:type="multipart/alternative">
      <next:multipart>
        <next:part next:lang="en" next:type="text/plain">Hello</next:part>
        <next:part next:lang="fr" next:type="text/plain">Bonjour</next:part>
      </next:multipart>
    </next:value>
  </content>
</rectangle>
```
