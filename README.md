# Code Convention

Code is clean if it can be understood easily – by everyone on the team. Clean code can be read and enhanced by a developer other than its original author. With understandability comes readability, changeability, extensibility and maintainability.
[Clean Code Lesson](https://www.youtube.com/watch?v=7EmboKQH8lM&list=PLmmYSbUCWJ4x1GO839azG_BBw8rkh-zOj)
[Clean Code Book](https://articulo.mercadolibre.cl/MLC-530498327-codigo-limpio-clean-code-manual-de-estilo-para-el-de-_JM?matt_tool=18461308&matt_word=&matt_source=google&matt_campaign_id=14571108129&matt_ad_group_id=127312331935&matt_match_type=&matt_network=g&matt_device=c&matt_creative=544390938376&matt_keyword=&matt_ad_position=&matt_ad_type=pla&matt_merchant_id=477912488&matt_product_id=MLC530498327&matt_product_partition_id=1413190260146&matt_target_id=aud-1660317627279:pla-1413190260146&gclid=Cj0KCQjw0oyYBhDGARIsAMZEuMvOmxUmtE_HJTpi-29JP_lr4IGNZN5H_hxkvASrQDF8HcwyZ7viXosaAke5EALw_wcB)
_____________________________________

## General rules
1. Follow standard conventions.
2. Keep it simple stupid. Simpler is always better. Reduce complexity as much as possible.
3. Boy scout rule. Leave the campground cleaner than you found it.
4. Always find root cause. Always look for the root cause of a problem.

## Design rules
1. Keep configurable data at high levels.
2. Prefer polymorphism to if/else or switch/case.
3. Separate multi-threading code.
4. Prevent over-configurability.
5. Use dependency injection.
6. Follow Law of Demeter. A class should know only its direct dependencies.

## Understandability tips
1. Be consistent. If you do something a certain way, do all similar things in the same way.
2. Use explanatory variables.
3. Encapsulate boundary conditions. Boundary conditions are hard to keep track of. Put the processing for them in one place.
4. Prefer dedicated value objects to primitive type.
5. Avoid logical dependency. Don't write methods which works correctly depending on something else in the same class.
6. Avoid negative conditionals.

## Names rules
1. Choose descriptive and unambiguous names.
2. Make meaningful distinction.
3. Use pronounceable names.
4. Use searchable names.
5. Replace magic numbers with named constants.
6. Avoid encodings. Don't append prefixes or type information.

## Functions rules
1. Small.
2. Do one thing.
3. Use descriptive names.
4. Prefer fewer arguments.
5. Have no side effects.
6. Don't use flag arguments. Split method into several independent methods that can be called from the client without the flag.

## Comments rules
1. Always try to explain yourself in code.
2. Don't be redundant.
3. Don't add obvious noise.
4. Don't use closing brace comments.
5. Don't comment out code. Just remove.
6. Use as explanation of intent.
7. Use as clarification of code.
8. Use as warning of consequences.

## Source code structure
1. Separate concepts vertically.
2. Related code should appear vertically dense.
3. Declare variables close to their usage.
4. Dependent functions should be close.
5. Similar functions should be close.
6. Place functions in the downward direction.
7. Keep lines short.
8. Don't use horizontal alignment.
9. Use white space to associate related things and disassociate weakly related.
10. Don't break indentation.

## Objects and data structures
1. Hide internal structure.
2. Prefer data structures.
3. Avoid hybrids structures (half object and half data).
4. Should be small.
5. Do one thing.    
6. Small number of instance variables.
7. Base class should know nothing about their derivatives.
8. Better to have many functions than to pass some code into a function to select a behavior.
9. Prefer non-static methods to static methods.

## Tests
1. One assert per test.
2. Readable.
3. Fast.
4. Independent.
5. Repeatable.

## Code smells
1. Rigidity. The software is difficult to change. A small change causes a cascade of subsequent changes.
2. Fragility. The software breaks in many places due to a single change.
3. Immobility. You cannot reuse parts of the code in other projects because of involved risks and high effort.
4. Needless Complexity.
5. Needless Repetition.
6. Opacity. The code is hard to understand.

# Commit Convention
The commit contains the following structural elements, to communicate intent to the consumers of your library

[Commit Convention](https://www.conventionalcommits.org/en/v1.0.0/#summary)

_____________________________________

1. fix: a commit of the type fix patches a bug in your codebase ***(this correlates with PATCH in Semantic Versioning)***.
```shell
     fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.

Remove timeouts which were used to mitigate the racing issue but are
obsolete now.
```
2. feat: a commit of the type feat introduces a new feature to the codebase ***(this correlates with MINOR in Semantic Versioning)***.
```shell
feat: allow provided config object to extend other configs
```
Commit message with ! to draw attention to breaking change
```shell
feat!: send an email to the customer when a product is shipped
```
Commit message with scope and ! to draw attention to breaking change
```shell
feat(api)!: send an email to the customer when a product is shipped
```

3. BREAKING CHANGE: a commit that has a footer BREAKING CHANGE:, or appends a ! after the type/scope, introduces a breaking API change ***(correlating with MAJOR in Semantic Versioning)***. 

A BREAKING CHANGE can be part of commits of any type.
types other than fix: and feat: are allowed, for example @commitlint/config-conventional (based on the the Angular convention) recommends build:, chore:, ci:, docs:, style:, refactor:, perf:, test:, and others. footers other than BREAKING CHANGE: <description> may be provided and follow a convention similar to git trailer format.

Additional types are not mandated by the Conventional Commits specification, and have no implicit effect in Semantic Versioning (unless they include a BREAKING CHANGE). A scope may be provided to a commit’s type, to provide additional contextual information and is contained within parenthesis, e.g., feat(parser): add ability to parse arrays.

## References
1. [Commit Convention](https://www.conventionalcommits.org/en/v1.0.0/#summary)
2. [commitlint](https://github.com/conventional-changelog/commitlint)
3. [Clean Code](https://articulo.mercadolibre.cl/MLC-530498327-codigo-limpio-clean-code-manual-de-estilo-para-el-de-_JM?matt_tool=18461308&matt_word=&matt_source=google&matt_campaign_id=14571108129&matt_ad_group_id=127312331935&matt_match_type=&matt_network=g&matt_device=c&matt_creative=544390938376&matt_keyword=&matt_ad_position=&matt_ad_type=pla&matt_merchant_id=477912488&matt_product_id=MLC530498327&matt_product_partition_id=1413190260146&matt_target_id=aud-1660317627279:pla-1413190260146&gclid=Cj0KCQjw0oyYBhDGARIsAMZEuMvOmxUmtE_HJTpi-29JP_lr4IGNZN5H_hxkvASrQDF8HcwyZ7viXosaAke5EALw_wcB)

