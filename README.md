# FTP-Sync extension for VS Code

This extension allows you to easily synchronise your local workspace (project files) with an FTP server. It also has several advanced features such as **automatic upload on save**.

![Demo of extension](https://i.imgur.com/W9h4pwW.gif)

## Usage

There are four commands available. You can access them from the command palette (Ctrl+Shift+P on Windows/Linux).

You can also sync a single file by right-clicking on it in the left menu and using the "Ftp-sync: Upload File" and "Ftp-sync: Download File" commands.

### Ftp-sync: Init

Initializes a default FTP-Sync configuration file in the `.vscode` directory. Options can be customised as follows:

- remotePath - This can be set to the path on the remote that you would like to upload to. The default is `./` i.e. the root.
- host - The hostname of the FTP server you want to connect to.
- username - The username of the FTP account you want to use.
- password - The password of the FTP account you want to use.
- port - The port on the FTP server you would like to connect to. The default is `"21"`.
- protocol - The FTP protocol to be used. The default is `"ftp"` but you can also specify `"sftp"`.
- uploadOnSave - Whether files should automatically be uploaded on save. The default is `false`.
- passive - Specifies whether to use FTP passive mode. The default is `false`.
- debug - Specifies whether to display debug information in an ftp-sync Output window. The default is `false`.
- privateKeyPath - Specifies the path to the private key for SFTP. The default is `null`.
- passphrase - Specifies the passphrase to use with the private key for SFTP. The default is `null`.
- agent - Specifies the ssh-agent to use for SFTP. The default is `null`.
- allow - An array of escaped regular expression strings specifying paths which are allowed. If nonempty, unless a path matches any of these regular expressions it will not be included in the sync. Default value is empty, implying everything is allowed.
- ignore - An array of escaped regular expression strings specifying paths to ignore. If a path matches any of these regular expressions then it will not be included in the sync. Default values are `"\\.git"`, `"\\.vscode"` and `".DS_Store"`.
- generatedFiles: - Automatically upload freshly generated files. Also uploads files that are deleted. extensionsToInclude has to be set for this feature to work.
  - extensionsToInclude: [] e.g. [".js", ".css"] - Array of strings specifying what extensions to add for auto-upload. An empty array here means that generatedFiles feature is disabled. Setting it to [""] will cause it to upload files of all extensions.
  - path: "" - This specifies the path to the directory where the files are, [e.g.] "/build", default is "" which is the root workspace directory

### Ftp-sync: Sync Local to Remote

Displays a synchronization wizard to configure a sync operation that changes FTP files and folders to match project files.

### Ftp-sync: Sync Remote to Local

Displays a synchronization wizard to configure a sync operation that changes project files and folders to match FTP files.

### Ftp-sync: Commit

Commits reviewed list of changes made with Sync Local to Remote or Sync Remote to Local command.

---

## To be added soon:

- Config validation (add minimal configuration requirement)
- Better connection error handling
- More real life testing
- Bug fixes
- Context menu to sync folders (up/down)

## Future plans

- Integration with git-ftp

### Found any bugs? Got any questions or ideas?

- Raise a ticket [on github issues](https://github.com/markhughes/vscode-ftp/issues)!

Please provide as much information as possible. We are dealing with diffrent ftp servers, file structures, file permissions, operating systems and it might be difficult to reproduce your error and fix it without detailed informations.

I'm looking forward to get any feedback from extension users! Contribution, especially on bug fixing is more than welcome!

Great thanks for suggestions and help with debugging for [Martin](https://github.com/kasik96), [Allan](https://github.com/EthraZa), [Maxime](https://github.com/maximedupre), [suuuunto](https://github.com/suuuunto) and all other folks who reported bugs or made improvement requests.

---

Use at your own risk - I do not guarantee that it will work correctly!

---
