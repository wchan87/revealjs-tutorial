# asciidoctor-revealjs

Derived primarily from [DZone > Presentation as Code: Why I Abandoned PowerPoint](https://dzone.com/articles/presentation-as-code-why-i-abandoned-powerpoint)

## JetBrains IDEs

If you're running into a rendering issue for asciidoctor-intellij-plugin, see [this page](https://github.com/asciidoctor/asciidoctor-intellij-plugin/issues/191).

## Visual Studio Code

In order to preview the diagrams on Visual Studio Code,

1. Run [Kroki gateway server](https://docs.kroki.io/kroki/setup/install/#_install_the_kroki_gateway_server)
    ```
    docker run -d --name kroki_gateway -p 8000:8000 yuzutech/kroki
    ```
2. Download [AsciiDoc](https://marketplace.visualstudio.com/items?itemName=asciidoctor.asciidoctor-vscode)
3. Enable `Use_kroki` via `Extension Settings` for `User`
4. Restart Visual Studio Code
5. Click the icon for `Open Preview to the Side`
6. Click the icon for `More Actions...` > `Change Preview Security Settings` > `Allow insecure local content`
6. Add the following under the title to [avoid calling](https://github.com/Mogztter/asciidoctor-kroki#using-your-own-kroki) the default Kroki gateway server online
    ```
    :kroki-server-url: http://localhost:8000
    ```

## Generate reveal.js HTML

1. Run the following [docker-asciidoctor](https://github.com/asciidoctor/docker-asciidoctor#how-to-use-it):
    ```
    docker run -it --rm -v $(pwd):/documents/ asciidoctor/docker-asciidoctor
    ```
    a. Execute the following command in the container
    ```
    asciidoctor-revealjs -a revealjsdir=https://cdnjs.cloudflare.com/ajax/libs/reveal.js/3.9.2 -r asciidoctor-diagram tutorial.adoc
    ```
