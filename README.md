
<p align="center">
	<img
		alt="In-game console for Godot Logo"
		width="128"
		src="assets/icon.svg"/>
</p>

Godot Console
============

<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-14-orange.svg?style=flat-square)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

![In-game console for Godot Screenshot](assets/screenshot.png)

In-game console for Godot, which could be easily extended with new commands.

- [Godot Console](#godot-console)
	- [Features](#features)
	- [Installation](#installation)
	- [Example usage](#example-usage)
	- [Contributors](#contributors-)
	- [License](#license)

## Features:

- Creating custom commands with [addCommand](godot/addons/quentincaffeino-console/docs/generated/Console.md#addCommand)

- Writing to console using [write](godot/addons/quentincaffeino-console/docs/generated/Console.md#write) and [writeLine](godot/addons/quentincaffeino-console/docs/generated/Console.md#writeLine) methods.
	You can also use [BB codes](https://godot.readthedocs.io/en/latest/learning/features/gui/bbcode_in_richtextlabel.html?highlight=richtextlabel#reference).

	(Is also printed to engine output)

- Session command history (by default using with actions `ui_up` and `ui_down`)
- [Flexible types](godot/addons/quentincaffeino-console/docs/Type.md):
	- [Engine types](godot/addons/quentincaffeino-console/docs/Type.md#engine-types)
	- [Extra types](godot/addons/quentincaffeino-console/docs/Type.md#extra-types)
	- [Custom types](godot/addons/quentincaffeino-console/docs/Type.md#creating-custom-types)
- [FuncRef](https://docs.godotengine.org/en/3.2/classes/class_funcref.html) support with Godot >=3.2 (can be used as a command target).

## Installation:

1. Clone this project or download latest release
2. Copy `./godot/addons/quentincaffeino-console` into your projects `addons` folder.
2. Enable console in Project/Addons
3. Add new actions to Input Map: `console_toggle`, `ui_up`, `ui_down`

## Example usage:

### Usage we will get:

```
$ sayHello "Adam Smith"
Hello Adam Smith!
```

### Function that will be called by our command:

```gdscript
func print_hello(name = ''):
	Console.write_line('Hello ' + name + '!')
```

### Registering command:

```gdscript
func _ready():
	# 1. argument is command name
	# 2. arg. is target (target could be a funcref)
	# 3. arg. is target name (name is not required if it is the same as first arg or target is a funcref)
	Console.add_command('sayHello', self, 'print_hello')\
		.set_description('Prints "Hello %name%!"')\
		.add_argument('name', TYPE_STRING)\
		.register()
```

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="http://gitlab.com/QuentinCaffeino"><img src="https://avatars3.githubusercontent.com/u/2855777?v=4" width="100px;" alt=""/><br /><sub><b>Sergei ZH</b></sub></a><br /><a href="https://github.com/quentincaffeino/godot-console/commits?author=quentincaffeino" title="Code">💻</a> <a href="#question-quentincaffeino" title="Answering Questions">💬</a> <a href="https://github.com/quentincaffeino/godot-console/commits?author=quentincaffeino" title="Documentation">📖</a> <a href="#ideas-quentincaffeino" title="Ideas, Planning, & Feedback">🤔</a> <a href="https://github.com/quentincaffeino/godot-console/pulls?q=is%3Apr+reviewed-by%3Aquentincaffeino" title="Reviewed Pull Requests">👀</a></td>
    <td align="center"><a href="http://www.underflowstudios.com"><img src="https://avatars3.githubusercontent.com/u/420072?v=4" width="100px;" alt=""/><br /><sub><b>Michael Brune</b></sub></a><br /><a href="#a11y-MJBrune" title="Accessibility">️️️️♿️</a> <a href="https://github.com/quentincaffeino/godot-console/issues?q=author%3AMJBrune" title="Bug reports">🐛</a></td>
    <td align="center"><a href="https://github.com/aganm"><img src="https://avatars0.githubusercontent.com/u/20380758?v=4" width="100px;" alt=""/><br /><sub><b>Michael Aganier</b></sub></a><br /><a href="https://github.com/quentincaffeino/godot-console/issues?q=author%3Aaganm" title="Bug reports">🐛</a></td>
    <td align="center"><a href="https://github.com/hpn33"><img src="https://avatars1.githubusercontent.com/u/16251202?v=4" width="100px;" alt=""/><br /><sub><b>hpn332</b></sub></a><br /><a href="https://github.com/quentincaffeino/godot-console/issues?q=author%3Ahpn33" title="Bug reports">🐛</a></td>
    <td align="center"><a href="https://github.com/danilw"><img src="https://avatars1.githubusercontent.com/u/24825887?v=4" width="100px;" alt=""/><br /><sub><b>Danil</b></sub></a><br /><a href="https://github.com/quentincaffeino/godot-console/issues?q=author%3Adanilw" title="Bug reports">🐛</a></td>
    <td align="center"><a href="http://sdnllc.com"><img src="https://avatars3.githubusercontent.com/u/2214652?v=4" width="100px;" alt=""/><br /><sub><b>Paul Hocker</b></sub></a><br /><a href="https://github.com/quentincaffeino/godot-console/issues?q=author%3Apaulhocker" title="Bug reports">🐛</a></td>
    <td align="center"><a href="https://github.com/SamanthaClarke1"><img src="https://avatars3.githubusercontent.com/u/24452702?v=4" width="100px;" alt=""/><br /><sub><b>Samantha Clarke</b></sub></a><br /><a href="https://github.com/quentincaffeino/godot-console/issues?q=author%3ASamanthaClarke1" title="Bug reports">🐛</a></td>
    <td align="center"><a href="https://hugo.pro"><img src="https://avatars3.githubusercontent.com/u/180032?v=4" width="100px;" alt=""/><br /><sub><b>Hugo Locurcio</b></sub></a><br /><a href="#a11y-Calinou" title="Accessibility">️️️️♿️</a></td>
  </tr>
  <tr>
    <td align="center"><a href="https://github.com/DmDerbin"><img src="https://avatars3.githubusercontent.com/u/6673326?v=4" width="100px;" alt=""/><br /><sub><b>Dmitry Derbin</b></sub></a><br /><a href="#question-DmDerbin" title="Answering Questions">💬</a></td>
    <td align="center"><a href="https://github.com/VitexHD"><img src="https://avatars0.githubusercontent.com/u/31520916?v=4" width="100px;" alt=""/><br /><sub><b>VitexHD</b></sub></a><br /><a href="https://github.com/quentincaffeino/godot-console/issues?q=author%3AVitexHD" title="Bug reports">🐛</a></td>
    <td align="center"><a href="https://github.com/hilfazer"><img src="https://avatars1.githubusercontent.com/u/29497869?v=4" width="100px;" alt=""/><br /><sub><b>hilfazer</b></sub></a><br /><a href="https://github.com/quentincaffeino/godot-console/commits?author=hilfazer" title="Code">💻</a></td>
    <td align="center"><a href="https://github.com/crazychenz"><img src="https://avatars2.githubusercontent.com/u/792769?v=4" width="100px;" alt=""/><br /><sub><b>Crazy Chenz</b></sub></a><br /><a href="https://github.com/quentincaffeino/godot-console/commits?author=crazychenz" title="Code">💻</a></td>
    <td align="center"><a href="https://github.com/Japortie"><img src="https://avatars2.githubusercontent.com/u/2089237?v=4" width="100px;" alt=""/><br /><sub><b>Marcus Schütte</b></sub></a><br /><a href="https://github.com/quentincaffeino/godot-console/commits?author=Japortie" title="Code">💻</a></td>
    <td align="center"><a href="https://github.com/Cryszon"><img src="https://avatars1.githubusercontent.com/u/5220970?v=4" width="100px;" alt=""/><br /><sub><b>Kimmo Salmela</b></sub></a><br /><a href="https://github.com/quentincaffeino/godot-console/commits?author=Cryszon" title="Code">💻</a></td>
  </tr>
</table>

<!-- markdownlint-enable -->
<!-- prettier-ignore-end -->
<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!

## License

Licensed under the MIT license, see `LICENSE.md` for more information.
