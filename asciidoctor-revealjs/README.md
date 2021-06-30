# asciidoctor-revealjs

Derived primarily from [DZone > Presentation as Code: Why I Abandoned PowerPoint](https://dzone.com/articles/presentation-as-code-why-i-abandoned-powerpoint)

Run the following [docker-asciidoctor](https://github.com/asciidoctor/docker-asciidoctor#how-to-use-it):
```
docker run -it -v $(pwd):/documents/ asciidoctor/docker-asciidoctor
```

Execute the following command in the container
```
asciidoctor-revealjs -a revealjsdir=https://cdnjs.cloudflare.com/ajax/libs/reveal.js/3.9.2 -r asciidoctor-diagram tutorial.adoc
```

If you're running into a rendering issue for asciidoctor-intellij-plugin, see [this page](https://github.com/asciidoctor/asciidoctor-intellij-plugin/issues/191).
