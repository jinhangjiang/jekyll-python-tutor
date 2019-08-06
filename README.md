# Embed Python Tutor Visualizations in Jekyll

Automatically embed [Python Tutor][] visualization buttons alongside your code
listings.

[Python Tutor]: http://pythontutor.com/

See [Java Crash Course][] for a live demo of the `java_visualizer.html`
include. Each "Visualize Code" button is automatically generated from the
preceding code listing.

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
    {% include java_visualizer.html code=HelloWorld caption="Hello, world!" %}
