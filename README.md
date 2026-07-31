# Knowledge Representation

## Introduction

Drawing inspiration from previous general-purpose knowledge-representation formats including [XML](https://en.wikipedia.org/wiki/XML), [HTML](https://en.wikipedia.org/wiki/HTML), [RDF](https://en.wikipedia.org/wiki/Resource_Description_Framework), [XUL](https://en.wikipedia.org/wiki/XUL), [XAML](https://en.wikipedia.org/wiki/Extensible_Application_Markup_Language), and [XOML](https://en.wikipedia.org/wiki/Extensible_Application_Markup_Language), this repository intends to serve as a forum for innovation and building consensus towards advancing existing knowledge-representation formats and/or proposing new such formats.

## A Quick Example

Expanding on some XAML/XOML concepts, envisioning a related knowledge-representation technology which binds to [JavaScript](https://en.wikipedia.org/wiki/JavaScript) while interoperable with the [Shadow DOM](https://en.wikipedia.org/wiki/Shadow_DOM) and [WebAssembly](https://en.wikipedia.org/wiki/WebAssembly), the following example showcases a number of markup-related techniques.

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

This format sketch, with _extended attributes_, would present opportunities for a new document object model atop the [DOM](https://en.wikipedia.org/wiki/Document_Object_Model).
