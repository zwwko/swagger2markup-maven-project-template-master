= Swagger2Markup Maven template project

This is a Swagger2Markup Maven template project which uses the swagger2markup-maven-plugin to convert a contract-first Swagger specification into an AsciiDoctor-based HTML documentation.

== Usage guide

=== Swagger Specification

. Copy your Swagger Specification (JSON or YAML) file into the folder `src/docs/swagger`
. Modify the `pom.xml` `properties.swagger.input` to point at the copied specification

=== Add hand-written content(增加手动写的内容)

Add hand-written AsciiDoc content into the folder `src/docs/asciidoc` and include the files in `src/docs/asciidoc/index.adoc`.

```
\include::{generated}/overview.adoc[]
\include::manual_content1.adoc[]
\include::manual_content2.adoc[]
\include::{generated}/paths.adoc[]
\include::{generated}/definitions.adoc[]
```

The Asciidoctor attribute `{generated}` is set by the Gradle script to `target/asciidoc`. By default the Swagger2Markup Maven plugin creates the the generated AsciiDoc files into the `target/asciidoc` folder.

=== Convert AsciiDoc into HTML

[source]
----
mvn process-resources
----

See `target/asciidoc/html5/index.html` to check the generated HTML report.


https://github.com/Swagger2Markup/swagger2markup-maven-project-template
http://swagger2markup.github.io/swagger2markup/1.3.1/#_swagger2markup_properties