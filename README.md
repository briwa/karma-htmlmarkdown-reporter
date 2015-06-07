# karma-htmlmarkdown-reporter

Reporter that formats results in HTML similar to jasmine. And Markdown file!

An improvement based on https://github.com/dtabuenc/karma-html-reporter, with an additional `README.md` Markdown file generated along with the HTML file.

This reporter basically generates HTML and Markdown file for your Karma test result based on the template `jasmine_html_template.html` and `jasmine_markdown_template.md`.

## Installation

The easiest way is to keep `karma-htmlmarkdown-reporter` as a devDependency in your `package.json`.
```json
{
  "devDependencies": {
    "karma": "~0.10",
    "karma-htmlmarkdown-reporter": "~0.1"
  }
}
```

You can simply do it by:
```bash
npm install karma-htmlmarkdown-reporter --save-dev
```

## Configuration
```js
// karma.conf.js
module.exports = function(config) {
  config.set({
    reporters: ['progress', 'html'],

    // the default configuration
    htmlReporter: {
      outputDir: 'karma_html', // where to put the reports 
      includeMarkdown: false, // whether you want a README.md file generated along with the HTML or not
      focusOnFailures: true, // reports show failures on start
      namedFiles: false, // name files instead of creating sub-directories
      pageTitle: null, // page title for reports; browser info by default
      urlFriendlyName: false, // simply replaces spaces with _ for files/dirs
      reportName: 'report-summary-filename', // report summary filename; browser info by default
      
      
      // experimental
      preserveDescribeNesting: false, // folded suites stay folded 
      foldAll: false, // reports start folded (only with preserveDescribeNesting)
    },
  });
};
```

You can pass list of reporters as a CLI argument too:
```bash
karma start --reporters html,dots
```

## Keyboard Controls

`1` and `2` - switch between Spec List and Failures.
`F` - fold/unfold all suites in `preserveDescribeNesting` mode.

----

For more information on Karma see the [homepage].

[homepage]: http://karma-runner.github.com

Kudos to the original author Daniel Tabuenca <dtabuenc@gmail.com> for making this awesome [reporter](https://github.com/dtabuenc/karma-html-reporter).
