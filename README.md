PART 1

# ffmpeg_mov_to_mp4

<details open>

<summary>Table of contents</summary>

- [What does it do?](#what-does-it-do)
- [Prerequisite](#prerequisite)
- [Setup](#setup)
- [Usage](#usage)
- [Linking](#linking)
	- [First step: Know your environment](#first-step-know-your-environment)
		- [Option 1: Via utility script](#option-1-via-utility-script)
		- [Option 2: By hand](#option-2-by-hand)
	- [Final step: Apply changes](#final-step-apply-changes)

</details>

---

## What does it do?

It creates a compressed copy of a large `.mov` file in the `.mp4` format using [`ffmpeg`](https://ffmpeg.org).

This is a simple function. It isn't very tolerant to fault.


## Prerequisite

You need to download and install [`ffmpeg`].

1. Download and Install Homebrew
```sh	
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
2. Install ffmpeg
```sh
brew install ffmpeg
```

## Setup

1. Follow the [Prerequisite](#prerequisite) instructions.

2. Clone this repository.
    ```sh
	git clone https://github.com/csantarin/ffmpeg_mp4_to_mov.git
    ```

3. Navigate to the repostitory folder.
	```sh
	cd <path/to/the/parent/of/your/local/copy>/ffmpeg_mov_to_mp4
	```

4. Expose the `ffmpeg_mov_to_mp4` function to command line.

	```sh
	source ./ffmpeg_mov_to_mp4.sh 
	```

5. Follow the [Linking](#linking) instructions to add this command to your command line permanently.

## Usage

Call the newly-installed `ffmpeg_mov_to_mp4` command.

```sh
# Call the function and provide an input file name
# - Include the trailing .mov extension.
# - Include a path (relative or absolute) if necessary.
ffmpeg_mov_to_mp4 <path/to/your/file>.mov
```

Example:

```sh
$ ffmpeg_mov_to_mp4 ../my-project/my-project-recording.mov

Processing ../my-project/my-project-recording.mov ...

# Some processing from the ffmpeg converter...

Done!
../my-project/my-project-recording.mp4
```

## Linking

In case you don't want to constantly `source` the same same command over and over, you can link the script.

### First step: Know your environment

You should locate where your shell environment is.

Assumptions in the subsequent parts:
- Shell environment file: `.zshrc`
- Location: user home directory (`~`. In the following, it represents the `/Users/csantarin` folder).

#### Option 1: Via utility script

There's a `link.sh` file that can do this for you.

```sh
sh ./link.sh ~/zshrc
```

Result:

```
Retrieving this repository's working directory ...
/Users/csantarin/ffmpeg_mov_to_mp4

Adding to /Users/csantarin/.zshrc ...
Done!
```

#### Option 2: By hand

Copy this to your shell environment file.

```sh
source ~/ffmpeg_mov_to_mp4/ffmpeg_mov_to_mp4.sh
```

### Final step: Apply changes

`source` the changes immediately or launch a new command line session:

```sh
source ~/.zshrc
```
