This project is an implementation of Git, developed as part of the Codecrafters "Build Your Own Git" challenge. It replicates core Git functionalities by implementing object storage, commit management, and references.

Features Implemented
✅ 1. Initializing a Repository (git init)

Creates the .git directory and subdirectories (objects, refs).
Sets up the HEAD file pointing to refs/heads/main.

✅ 2. Handling Git Objects (git hash-object, git cat-file)

Blob creation: Reads file content, computes its SHA-1 hash, and stores it in .git/objects/.
Object retrieval: Reads and decompresses objects from .git/objects/.

✅ 3. Tree and Commit Management (git write-tree, git commit-tree, git commit)

Tree objects: Converts the directory structure into a Git tree.
Commit objects: Links trees and parent commits, storing metadata like message, author, and timestamp.
Commit referencing: Updates .git/refs/ with commit hashes.

✅ 4. Listing Tree Contents (git ls-tree)

Parses and displays tree objects


Prerequisites
Rust installed (rustc --version)

Cargo package manager

Building the Project
cargo build --release

Running the CLI

cargo run -- git init

cargo run -- git hash-object -w <file>

cargo run -- git cat-file -p <hash>

cargo run -- git write-tree

cargo run -- git commit-tree -m "Message" -p <parent_hash> <tree_hash>

cargo run -- git commit -m "Commit message"


Conclusion
This project provides a deeper understanding of Git internals, including object storage, commits, and references. 


#Below are the CodeCrafters Instrucions



This is a starting point for Rust solutions to the
["Build Your Own Git" Challenge](https://codecrafters.io/challenges/git).

In this challenge, you'll build a small Git implementation that's capable of
initializing a repository, creating commits and cloning a public repository.
Along the way we'll learn about the `.git` directory, Git objects (blobs,
commits, trees etc.), Git's transfer protocols and more.

**Note**: If you're viewing this repo on GitHub, head over to
[codecrafters.io](https://codecrafters.io) to try the challenge.

# Passing the first stage

The entry point for your Git implementation is in `src/main.rs`. Study and
uncomment the relevant code, and push your changes to pass the first stage:

```sh
git add .
git commit -m "pass 1st stage" # any msg
git push origin master
```

That's all!

# Stage 2 & beyond

Note: This section is for stages 2 and beyond.

1. Ensure you have `cargo (1.54)` installed locally
1. Run `./your_git.sh` to run your Git implementation, which is implemented in
   `src/main.rs`. This command compiles your Rust project, so it might be slow
   the first time you run it. Subsequent runs will be fast.
1. Commit your changes and run `git push origin master` to submit your solution
   to CodeCrafters. Test output will be streamed to your terminal.

# Testing locally

The `your_git.sh` script is expected to operate on the `.git` folder inside the
current working directory. If you're running this inside the root of this
repository, you might end up accidentally damaging your repository's `.git`
folder.

We suggest executing `your_git.sh` in a different folder when testing locally.
For example:

```sh
mkdir -p /tmp/testing && cd /tmp/testing
/path/to/your/repo/your_git.sh init
```

To make this easier to type out, you could add a
[shell alias](https://shapeshed.com/unix-alias/):

```sh
alias mygit=/path/to/your/repo/your_git.sh

mkdir -p /tmp/testing && cd /tmp/testing
mygit init
```
# GitFoundry-Built_My_Own-Git_from_Scratch
