# Oberon TSlint config & standard

The Oberon typescript code standard & config.

## Codestyle

### The gist  

- **Semicolons at the end of each statement.**
- **camelCasing should be used on all object properties.**
- **Always use [curly brace conventions](https://eslint.org/docs/rules/curly).** Even if your block only consists of a single statement. 
- **Single quotes are the default.** But use double quotes within JSX. 
- **Indents with 4 spaces**, no tabs allowed.
- **Always use === for comparing equality**
- **Don't use var**, use const/let instead.
- **Don't declare multiple variables on a single line.** Except for uninitialized variables.
This is **allowed**:
```js
const a, b, c;
```  
This **isn't:**
```js
const a = false, b = true, c = false;
```

### Full set

Read the set of rules here [here](https://github.com/oberonamsterdam/tslint-config-oberon/blob/master/tslint-config-oberon.json)
Additionally, be aware of the [tslint recommended rules](https://github.com/palantir/tslint/blob/master/src/configs/recommended.ts), they also apply.

## Usage
Add a `tslint.json` file to your project:  


```json
{
    "extends": ["tslint-config-oberon"]
}
```

Install tslint & tslint-config-oberon locally (`npm i -D tslint tslint-config-oberon`)
Optionally, add tslint as a precommit hook by installing [husky](https://github.com/typicode/husky) (`npm i -D husky`) and adding a `precommit` script to your package.json `scripts`:
```json
{
      "scripts": {
           ...
          "precommit": "tslint --project ."  
      }
}

```
### Optional prettier setup:

In order to enforce good practices concerning code quality, it is advised to let prettier handle the code formatting and tslint the semantics and syntax. To install prettier please follow the readme of the [oberon-config-prettier](https://github.com/oberonamsterdam/prettier-config-oberon). To resolve conflicts between tslint and prettier you also need to install tslint-config-prettier (`npm i -D tslint-config-prettier`) and add it to the `tslint.json` file:

```json
{
    "extends": ["tslint-config-oberon", "tslint-config-prettier"]
}
```
