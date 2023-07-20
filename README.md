# ECMAScript `try`/`catch` expressions

This proposal defines new syntax to try and catch exceptions from within an expression context.

## Status

**Stage:** 0
**Champion:** Lino Le Van (@lino-levan)

_For more information see the [TC39 proposal process](https://tc39.github.io/process-document/)._

## Authors

* Lino Le Van (@lino-levan)

# Proposal

A `try`/`catch` expression allows you to perform error handling in expression contexts. For example:

```js
const value = try riskyFunction() catch "default_value";
```

# Grammar

TODO

# Other Notes

TODO: Discuss prior art
- https://github.com/dead-claudia/proposal-try-expression


A `try`/`catch` expression can be approximated in ECMAScript using something like the following definition:

```js
const try_catch = (op1, op2) => {
  try {
    return op1();
  }
  catch {
    return op2();
  }
};

const value = try_catch(()=>riskyFunction(), ()=>"default_value");
```

However, this has several downsides compared to a native implementation:
* Inline functions, even with arrow functions, are not ergonomic to type
* TODO

# Resources

TODO (Overview slides)

# TODO

The following is a high-level list of tasks to progress through each stage of the [TC39 proposal process](https://tc39.github.io/process-document/):

### Stage 1 Entrance Criteria

* [ ] Identified a "[champion][Champion]" who will advance the addition.  
* [ ] [Prose][Prose] outlining the problem or need and the general shape of a solution.  
* [ ] Illustrative [examples][Examples] of usage.  
* [ ] ~High-level API~ _(proposal does not introduce an API)_.  

### Stage 2 Entrance Criteria

* [ ] [Initial specification text][Specification].  
* [ ] _Optional_. [Transpiler support][Transpiler].  

### Stage 3 Entrance Criteria

* [ ] [Complete specification text][Specification].  
* [ ] Designated reviewers have [signed off][Stage3ReviewerSignOff] on the current spec text.  
* [ ] The ECMAScript editor has [signed off][Stage3EditorSignOff] on the current spec text.  

### Stage 4 Entrance Criteria

* [ ] [Test262](https://github.com/tc39/test262) acceptance tests have been written for mainline usage scenarios and [merged][Test262PullRequest].  
* [ ] Two compatible implementations which pass the acceptance tests: [\[1\]][Implementation1], [\[2\]][Implementation2].  
* [ ] A [pull request][Ecma262PullRequest] has been sent to tc39/ecma262 with the integrated spec text.  
* [ ] The ECMAScript editor has signed off on the [pull request][Ecma262PullRequest].  

<!-- The following are shared links used throughout the README: -->

[Champion]: #status
[Prose]: #proposal
[Examples]: #proposal
[Specification]: #todo
[Transpiler]: #todo
[Stage3ReviewerSignOff]: #todo
[Stage3EditorSignOff]: #todo
[Test262PullRequest]: #todo
[Implementation1]: #todo
[Implementation2]: #todo
[Ecma262PullRequest]: #todo
