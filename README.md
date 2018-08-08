# Embed Python Tutor Visualizations in Jekyll

Inspired by inline interactive visualizations in [Composing Programs][] and a
desire for better visualization tools for students in lab-centric instruction
courses, this Liquid include makes it easy to embed visualizations on any
Jekyll website, including websites hosted on GitHub Pages.

[Composing Programs]: http://composingprograms.com/

This embed was originally developed for [CS 61BL Summer 2018][]. See the [Java
Crash Course][] for a live demonstration of the `java_visualizer.html` include.

[CS 61BL Summer 2018]: https://cs61bl.org/su18/
[Java Crash Course]: https://cs61bl.org/su18/java/

## Usage

Download the appropriate visualization embed from [`_includes`](/_includes)
into your Jekyll website's `_includes` folder. Then, follow the usage
instructions in the file.

As an example, here's a sample for embedding the
[`java_visualizer.html`](/_includes/java_visualizer.html).

    {%- capture HelloWorld -%}
    public class HelloWorld {
        public static void main(String[] args) {
            System.out.println("Hello, world!");
        }
    }
    {%- endcapture -%}
    {% include java_visualizer.html
        embed=true caption="Hello, world!" code=HelloWorld
        height="480px" curInstr="0" args='["arg1", ...]' stdin="stdin" %}

## Frequently Asked Questions

### Why use the online Java Visualizer instead of Python Tutor's Java instance?

Currently, the Online Python Tutor web service does not support https.  Modern
web browsers disallow [mixed active content][] including `iframe` used to embed
the visualization. Unfortunately, there [don't seem to be any plans to switch
to https][embed python tutor on https page] through the free Python Tutor web
service.

The workaround in `java_visualizer.html` is to instead use University of
Waterloo's freely-hosted Python Tutor instance based on David Pritchard and
Will Gwozdz's [java_jail][] and [java_visualize][] spinoff. This implementation
has a few neat frontend features as well that make it more useful than the
current version of the Online Python Tutor as well.

[mixed active content]: https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content#Mixed_active_content
[embed python tutor on https page]: https://github.com/pgbovine/OnlinePythonTutor/issues/155
[java_jail]: https://github.com/daveagp/java_jail
[java_visualize]: https://github.com/daveagp/java_visualize
