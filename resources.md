# Resources

- EIP templates - [The description of the EIP format](https://eips.ethereum.org/EIPS/eip-1#eip-formats-and-templates)

## Linting

- https://eips.ethereum.org/EIPS/eip-1#eip-formats-and-templates
- https://docs.rs/comrak/latest/comrak/nodes/struct.Ast.html - Ast
- https://en.wikipedia.org/wiki/Visitor_pattern

Each lint is a struct that implements an interface Lint.
**fn find_resources()** - contents of different files: checking the file exists, checking the status of another proposal. Most of the time you don’t need it.
**fn lint()** - generate the errors for the text you’re checking.

Markdown is represented as a tree of nodes. Each node can have children.

We use [Ast](https://docs.rs/comrak/latest/comrak/nodes/struct.Ast.html) to get the line number of the code where the error happened.

### Run Lint

Download ethereum/eips or create your \*.md file with eip. Run lint on this file:
eipw (your-branch) > cargo run -- <path-to-eip-folder>/EIPs/EIPS/eip-1485.md

## Tests

**eipw/eipw-lint/tests - integration tests**, they can only see public interface, emulating people using your library. They can’t see private members of the modules.

**Unit tests** internal to your library. #[cfg(test)] in the code.

For this repo we use mostly integration tests because the lints are externally visible.

Specific EIPW tests:

- Regular integration tests
- Inherited from an older project (eipv)

Run tests (runs both integration and unit tests):

```
> cargo test
```

Command to only run the test for your specific file
In the eipw-lint folder run:
eipw/eipw-lint/tests> cargo test --test <test_name>

Example:

```
eipw/eipw-lint/tests> cargo test --test lint_markdown_link_first
```

! Don’t use “.rs” extension of your test file

You can also use VSCode extensions to run tests. Press “Run Test” in the code for a specific test. Press “Debug” for debugging. Extensions installation is below.

## Setting up VSCode Rust Extensions

https://gigi.nullneuron.net/gigilabs/getting-started-with-rust-using-vs-code/

## GitHub

Get started: https://docs.github.com/en/authentication/connecting-to-github-with-ssh

- Cherry pick:
  https://www.youtube.com/watch?v=skPB3ZRYyL4
- Creating fork, pull request:
  https://www.youtube.com/watch?v=8A4TsoXJOs8

Games to learn:

- https://ohmygit.org/
- https://dev.to/pradumnasaraf/want-to-learn-about-git-and-github-in-a-more-fun-way-4o5f
