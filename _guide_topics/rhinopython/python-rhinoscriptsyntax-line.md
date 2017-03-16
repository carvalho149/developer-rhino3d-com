---
title: Lines in Python
description: This guide provides an overview of a RhinoScriptSytntax Line Geometry in Python.
authors: ['Dale Fugier']
author_contacts: ['dale']
apis: ['RhinoPython']
languages: ['Python']
platforms: ['Mac', 'Windows']
categories: ['Python in Rhino']
origin:
order: 4
keywords: ['script', 'Rhino', 'python']
layout: toc-guide-page
---

## Lines

3-D lines, or chords, are stored as [Line]({{ site.baseurl }}/api/RhinoCommonWin/html/T_Rhino_Geometry_Line.htm) structures.  A Line represented as  zero-based, one-dimensional arrays that contain two elements:  the starting [point]({{ site.baseurl }}/guides/rhinopython/python-rhinoscriptsyntax-points) and the ending  [point]({{ site.baseurl }}/guides/rhinopython/python-rhinoscriptsyntax-points).  A line can be constructed in a number of different ways.  For example:

```python
startPoint = [1.0, 2.0, 3.0]
endPoint = [4.0, 5.0, 6.0]
line1 = [startPoint, endPoint]
```

To add the line to the current Rhino file, and see it drawn on screen, you can use the `AddLine` method in RhinoscriptSytnax:

```python
import rhinoscriptsyntax as rs

startPoint = [1.0, 2.0, 3.0]
endPoint = [4.0, 5.0, 6.0]
line1 = [startPoint, endPoint]

lineID = rs.AddLine(line1[0],line1[1])
```

When adding geometry to Rhino, rhinoscriptsyntax will return an 'Object ID' for the added object. The Rhino file has the object added as geometry in the file. Just like an object added using a Rhino command, it has an ID that is a unique reference to this object. This makes it possible and easy to get access to the specific object later in the script.  Saving this ID in a variable or a list is what allows it to be used later to select and manipulate the object.

Of course you could also send the `startPoint` and the `endPoint` directly into the `rs.AddLine()` method to create the line in Rhino.

RhinoScript contains a number of methods to manipulate lines.  See [Lines and Planes]({{ site.baseurl }}/guides/rhinopython/python-rhinoscriptsyntax-line-plane-methods) for details.

---

## Related Topics

- [What is Python and RhinoScript?]({{ site.baseurl }}/guides/rhinopython/what-are-python-rhinoscript)
- [Python Points]({{ site.baseurl }}/guides/rhinopython/python-rhinoscriptsyntax-points)
- [Python Vectors]({{ site.baseurl }}/guides/rhinopython/python-rhinoscriptsyntax-vectors)
- [Python Lines]({{ site.baseurl }}/guides/rhinopython/python-rhinoscriptsyntax-lines)
- [Python Planes]({{ site.baseurl }}/guides/rhinopython/python-rhinoscriptsyntax-planes)
- [Python Objects]({{ site.baseurl }}/guides/rhinopython/python-rhinoscriptsyntax-objects)
