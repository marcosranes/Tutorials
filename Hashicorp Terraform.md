# Terraform Installation with Apt
## Requirements: 
1. You'll need a Client URL tool installed 
```
sudo apt install curl
```
2. Add a gpg key
```
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
```
3. Add Hashicorp repository
```
sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
```
4. Fetch the apt repository and install Terraform
```
sudo apt update && sudo apt install terraform -y
```
5.  Pattern path
```
which terraform
...
/usr/bin/terraform
```
6. Version
```
terraform --version
...
Terraform v1.1.8
on linux_amd64
```
7. Usage
```
terraform --help
...
Usage: terraform [global options] <subcommand> [args]

The available commands for execution are listed below.
The primary workflow commands are given first, followed by
less common or more advanced commands.

Main commands:
  init          Prepare your working directory for other commands
  validate      Check whether the configuration is valid
  plan          Show changes required by the current configuration
  apply         Create or update infrastructure
  destroy       Destroy previously-created infrastructure

All other commands:
  console       Try Terraform expressions at an interactive command prompt
  fmt           Reformat your configuration in the standard style
  force-unlock  Release a stuck lock on the current workspace
  get           Install or upgrade remote Terraform modules
  graph         Generate a Graphviz graph of the steps in an operation
  import        Associate existing infrastructure with a Terraform resource
  login         Obtain and save credentials for a remote host
  logout        Remove locally-stored credentials for a remote host
  output        Show output values from your root module
  providers     Show the providers required for this configuration
  refresh       Update the state to match remote systems
  show          Show the current state or a saved plan
  state         Advanced state management
  taint         Mark a resource instance as not fully functional
  test          Experimental support for module integration testing
  untaint       Remove the 'tainted' state from a resource instance
  version       Show the current Terraform version
  workspace     Workspace management

Global options (use these before the subcommand, if any):
  -chdir=DIR    Switch to a different working directory before executing the
                given subcommand.
  -help         Show this help output, or the help for a specified subcommand.
  -version      An alias for the "version" subcommand.
```
8. Unistall Terraform
```
sudo apt purge terraform
```
# Terraform Installation through download
## Requirements:
1. Know which architecture your distro Lunux is under
```
dpkg --print-architecture
...
amd64
```
2. Download [Terraform](https://www.terraform.io/downloads). Go to LINUX BINARY DOWNLOAD, chose your archtecture, so click the right button mouse,\
then click `Copy link address` in dropdown, go to the terminal and type `wget -O /tmp/terraform.zip <past the link you copy earlier>`, press enter.
```
wget -O /tmp/terraform_installer.zip https://releases.hashicorp.com/terraform/1.1.8/terraform_1.1.8_linux_amd64.zip
```
3. Unzip terraform_installer.zip file and send it straight to its pattern destination
```
sudo unzip -d /usr/local/bin /tmp/terraform_installer.zip
```
Otherwise...
```
sudo unzip -d /usr/bin /tmp/terraform_installer.zip
```
4. Confirm whether the Terraform's executable file was properly extracted
```
ls /usr/local/bin
ls /usr/bin | grep terra
...
terraform
```
5. Also try those commands. The first one prints the terraform's path, and the second one the terraform's version
```
which terraform
...
terraform --version
```
6. Uninstall Terraform
```
sudo rm $(which terraform)
...
sudo rm $(which terraform) -f
```