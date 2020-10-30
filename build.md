## Build


```bash
cargo build
cargo run
```

This command quickly checks your code to make sure it compiles but doesn't produce an executable.
```bash
cargo check
```

### Ensuring Reproducible Builds with the Cargo.lock File
Cargo has a mechanism that ensures you can rebuild the same artifact every time you or anyone else builds your code: Cargo will use only the versions of the dependencies you specified until you indicate otherwise. For example, what happens if next week version 0.5.6 of the rand crate comes out and contains an important bug fix but also contains a regression that will break your code?

The answer to this problem is the Cargo.lock file, which was created the first time you ran cargo build and is now in your guessing_game directory. When you build a project for the first time, Cargo figures out all the versions of the dependencies that fit the criteria and then writes them to the Cargo.lock file. When you build your project in the future, Cargo will see that the Cargo.lock file exists and use the versions specified there rather than doing all the work of figuring out versions again. This lets you have a reproducible build automatically. In other words, your project will remain at 0.5.5 until you explicitly upgrade, thanks to the Cargo.lock file.
