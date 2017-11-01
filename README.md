# Rust notes
Personal list of links to blog posts, articles, videos and notes for learning Rust

## Getting started
* [Installation](https://www.rust-lang.org/)
* [Web playground](https://play.rust-lang.org/)
* [Documentation](https://www.rust-lang.org/en-US/documentation.html)
* [rust-learning](https://github.com/ctjhoa/rust-learning)

## IDEs
* [Visual Studio Code](https://code.visualstudio.com/)
	* [Rust (rls)](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust)
* [IntelliJ IDEA](https://www.jetbrains.com/idea/)
	* [IntelliJ Rust plugin](https://intellij-rust.github.io/)

## Other materials
* [Awesome Rust](https://github.com/rust-unofficial/awesome-rust)
* [Fun facts about Rust's growing popularity](http://www.jonathanturner.org/2017/10/fun-facts-about-rust-growth.html)
* [Chucklefish AMA](https://www.reddit.com/r/rust/comments/78bowa/hey_this_is_kyren_from_chucklefish_we_make_and/)

## Notes
**Scripts for optimized single file builds**

brust.cmd (add to system PATH)
```Batchfile
rustc -C opt-level=3 -C lto -C target-cpu=native %1
```

brust (place in /usr/local/bin/)
```Shell
#!/bin/bash
rustc -C opt-level=3 -C lto -C target-cpu=native $1
```

**Settings for optimized cargo builds**

.cargo/config (place in project root)
```TOML
[build]
rustflags = ["-C", "target-cpu=native", "-C", "opt-level=3"]

[term]
#verbose = true
```

cargo.toml
```TOML
[profile.release]
lto = true
panic = 'abort'
```
