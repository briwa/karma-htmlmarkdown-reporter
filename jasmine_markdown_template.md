{{pageTitle}}
=============
Tested in {{browserName}} on {{date}}

## Summary
{{#results}}
  {{total}} specs, {{failed}} failed, {{skipped}} pending
{{/results}}

## Result
{{^sections}}
{{#suites}}
### {{name}}
Status: {{state}}
{{#specs}}
- {{description}}

  Status: {{state}}
  {{#time}}
  Finished in {{time}}
  {{/time}}
  {{#log}}
  ```javascript
  {{log}}
  ```
{{/log}}
{{/specs}}
=== 
{{/suites}}
{{/sections}}
