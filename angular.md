# Angular Cheat-Sheet

## Terminal Commands

- node -v 
  - gives node.js version
- npm -v
  - gives npm version
- ng --version
  - gives versions of the angular cli and several related libraries and tools
- npm uninstall -g angular-cli
  - to update the cli, you first must uninstall the cli
- npm install -g @angular/cli@latest
  - installs the latest cli
- Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
  - used this command to get the cli working?? No idea why it worked
  - See [this link]: http://www.techtutorhub.com/article/Getting-ng-File-AppData-Roaming-npm-ng-ps1-cannot-be-loaded-The-file-npm-ng-ps1-is-not-digitally-signed-Angular-Error-when-running-commands/62
- ng new tour-of-heroes
  - creates a new angular project in current folder with the given name
- npm start
  - runs ng serve, spinning up app on port 4200 in your browser
- ng update @angular/cli @angular/core
  - upgrades your current application to the lastest v of angular. (may need to update cli first?)