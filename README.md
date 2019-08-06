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

### [`pytutor_visualizer.html`](/_includes/pytutor_visualizer.html)

    {%- capture HelloWorld -%}
    print('Hello, world!')
    {%- endcapture -%}
    {% include pytutor_visualizer.html py="3" code=HelloWorld caption="Hello, world!" %}

The full list of `py` [backend language flags][] can be found in Philip's repo.

[backend language flags]: https://github.com/pgbovine/OnlinePythonTutor/blob/80ac1ac1b832e94d279d76af7c40bb0e3944d768/v5-unity/visualize.html#L48-L56

### [`java_visualizer.html`](/_includes/java_visualizer.html)

    {%- capture HelloWorld -%}
    public class HelloWorld {
        public static void main(String[] args) {
            System.out.println("Hello, world!");
        }
    }
    {%- endcapture -%}
    {% include java_visualizer.html code=HelloWorld caption="Hello, world!" %}
