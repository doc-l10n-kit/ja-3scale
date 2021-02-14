# ja-3scale

Localization project for [3scale.github.io](https://github.com/3scale/3scale.github.io) (The repository for [3scale.github.io website](https://3scale.github.io))

Localized site: [https://ja-3scale.surge.sh/](https://ja-3scale.surge.sh)

## Translation workflow

Original [3scale.github.io](https://github.com/3scale/3scale.github.io) is built with Jekyll, and its contents are written in asciidoctor (.adoc) files.
ja-3scale extracts texts with [po4a](https://po4a.org/) utility, machine-translates with deepL, write back, and build a localized site.
Most workflow are automated by GitHub Actions except manual post-editing(translation). If you are interested in contributing localization,
please translate .po files, and submit a pull request.

### Prerequisites

All you need for your local environment is a CAT Tool like [POEdit](https://poedit.net/), which run on Win/Mac/Linux.

### Extracting texts from original repository

ja-3scale extracts texts with [po4a-updatepo](https://po4a.org/) utility from .adoc files to .adoc.po files, which saved in 
in [l10n/po](l10n/po) directory.
ja-3scale GitHub repository has a [GitHub Actions' periodic workflow](.github/workflows/sync-upstream.yml) 
to extract texts from .adoc files stored in upstream submodule, 
which points [3scale.github.io](https://github.com/3scale/3scale.github.io) repository.

### Translating .po files

.po files in [l10n/po](l10n/po) directory need to be translated. 
.po file is a file format commonly used for software internationalization, and many CAT software and SaaS can read/write.
While generating .po files, texts are pre-filled with translation memory and machine translation. 
Please correct inappropriate sentences if needed.

### Applying translated texts

Now you are ready to apply translated texts to .adoc files. With the command below, translated source tree are formed in `translated` directory.

```
bin/apply-translation
```

### Build a translated site

You can build a translated site from `translated` directory with:

```
bin/exec-jekyll
```

## Contributing

Submitting a pull request, and reporting an issue are all welcome.

For translators, we have a [translation guide(ja)](./translation-guide.ja.md).

## License

ja-3scale is Open Source Project released under the
[Apache 2.0 license](http://www.apache.org/licenses/LICENSE-2.0.html).
