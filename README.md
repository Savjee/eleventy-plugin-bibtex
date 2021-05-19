# eleventy-plugin-bibtex

Converts Bibtex references to APA notation in HTML

## Installation
Install with npm:

```
npm install --save-dev eleventy-plugin-bibtex
```

Add to your `.eleventy.js` config file:

```js
eleventyConfig
    .addPairedShortcode("bibtex", require('eleventy-plugin-bibtex'));
```

## Usage
In Liquid:

```liquid
{% bibtex %}
@article{kocher2018spectre,
  title={Spectre Attacks: Exploiting Speculative Execution},
  author={Kocher, Paul and Genkin, Daniel and Gruss, Daniel and Haas, Werner and Hamburg, Mike and Lipp, Moritz and Mangard, Stefan and Prescher, Thomas and Schwarz, Michael and Yarom, Yuval},
  journal={arXiv preprint arXiv:1801.01203},
  year={2018},
  url={https://arxiv.org/pdf/1801.01203},
}
{% endbibtex %}
```

Will output:

```html
<div data-csl-entry-id="2" class="csl-entry">Kocher, P., Genkin, D., Gruss, D., Haas, W., Hamburg, M., Lipp, M., Mangard, S., Prescher, T., Schwarz, M., &amp; Yarom, Y. (2018). Spectre Attacks: Exploiting Speculative Execution. <i>ArXiv Preprint ArXiv:1801.01203</i>. <a href="https://arxiv.org/pdf/1801.01203" class="no-underline no-underline-url" target="_blank" rel="noopener noreferrer">https://arxiv.org/pdf/1801.01203</a></div>
```

## Notes

* If the output APA contains URLs, it will create actual `a hrefs` for them using [Autolinker.js](https://github.com/gregjacobs/Autolinker.js).

* Bibtex requires unique IDs for all citations. This plugin does not require that, so be aware of possible duplicates.