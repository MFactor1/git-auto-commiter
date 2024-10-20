# git-auto-commiter (GAC)
Students around the world use Git to manage academic projects, where frequent commits are often required to maintain academic integrity. git-auto-commiter (GAC) is a CLI tool created by students, for students, to promote transparency throughout the academic process. GAC automates the creation of consistent, traceable, and reliable commits at scheduled intervals, allowing students to focus on their work without manual interruptions. By automatically committing on behalf of the user, GAC provides a clear record of project progress over time.

GAC gives students peace of mind, knowing they don’t need to worry about frequent manual commits, while instructors benefit from a detailed history of the students' work, readily available for review.
With the ability to track multiple repositories simultaneously each with their own commit schedule, GAC can handle all your projects at once, while only making new commits on the repositories that actually have changes.

## Requirements
- A Linux or other UNIX-like system using systemd (WSL not yet supported)
- An installation of python >= 3.5
- An installation of the gevent python package (Try: `pip install gevent`)

## Installation
Currently the only installation method is via the install script, other methods are not _yet_ available.
Clone this repo, and run the install script with sudo:
``` sh
git clone git@github.com:MFactor1/git-auto-commiter.git
cd git-auto-commiter
sudo ./install
```

Similarily, uninstallation can be completed via the uninstall script found in this repo:
``` sh
git clone git@github.com:MFactor1/git-auto-commiter.git
cd git-auto-commiter
sudo ./uninstall
```

Note: After installation, the cloned repo can be safely deleted. Hint: the uninstall script is placed in `/usr/local/lib/gac/` upon installation, so you can always find it there.

## Usage
- `gac add <name> <interval> <path>`: Adds tracker with name `<name>` with commit frequency of `<interval>` minutes, to repo at path `<path>`.
- `gac remove <name>`: Removes tracker with name `<name>`.
- `gac list [-m, --machine]`: Lists the all the active trackers. `-m` option produces a more script friendly output.
- `gac status`: Prints the status of the GAC daemon (active/inactive). GAC **requires** the GAC daemon to be **active** in order to create commits.
- `gac start`: Starts the GAC daemon.
- `gac stop`: Stops the GAC daemon.
- `gac enable`: Enables run on startup for the GAC daemon.
- `gac disable`: Disables run on startup for the GAC daemon.
- `gac -v, --version`: prints version information.
- `gac -h, --help`: prints a help message.
