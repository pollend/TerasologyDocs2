Adding new languages to the game or helping out with translating single strings is easy and helpful as it allows players from all over the world to enjoy the game, unhindered by language barriers!

## Introduction

There are currently two ways of translating the game:

1. (**Recommended**) Using our [Weblate](http://weblate.org) web interface at [translate.terasology.org](http://translate.terasology.org/).
2. Manually creating or editing text bundle files.

The former is the better option, as it allows us to easily review new translations or suggested changes. 

## Using Weblate

To start off, log in to [translate.terasology.org](http://translate.terasology.org/). The preferable login method is using your GitHub account - by doing so, your changes and translations will be recognized correctly in the Git commits. 

All translations needed for Terasology can be found in the corresponding Weblate project - **[Weblate/Terasology](http://translate.terasology.org/projects/terasology/)**. The project contains a single subproject: *Menu*, where all of the strings, labels and error messages for the game's main menu can be translated. This sub-project is found under **[Weblate/Terasology/Menu](http://translate.terasology.org/projects/terasology/menu/)**.

If your language doesn't exist in the round-up yet, you can request the addition of it using the **New translation** panel in the Menu sub-project. Otherwise, pick an existing language and translate away! Note that since English is the launcher's default language, English strings can only be modified using [manual translation](#manual-translation).

For more information on how to use Weblate, see the official [Translator guide](http://weblate.readthedocs.org/en/weblate-2.1/user/translating.html) for Weblate 2.1.

## Manual Translation

First off, to keep things nice and clean, we advise you to work on the translation using a **feature branch**:

  * `git checkout develop`
  * `git branch feature/myTranslation`
  * `git checkout feature/myTranslation`
  
To create a new language file, copy [`menu_en.lang`](https://github.com/MovingBlocks/Terasology/blob/develop/engine/src/main/resources/assets/i18n/menu_en.lang) to a new file called `menu_xx.lang` in [`engine/src/main/resources/assets/i18n`](https://github.com/MovingBlocks/Terasology/blob/develop/engine/src/main/resources/assets/i18n/) - `xx` should be an [ISO 639-1](http://en.wikipedia.org/wiki/ISO_639-1) two-letter code for your language. Next up, translate everything in `menu_xx.lang` to your target language! Every now and then, check up on your in-progress translation - the game's language can be changed in the *Settings - Player* menu. Some possible issues that may occur are long strings breaking UI elements and special characters not being rendered properly.

When your translation is finished, add a tiny flag to represent the language in the settings! To do this, download an appropriate 16x11 icon from the [famfamfam.com icon pack](http://www.famfamfam.com/lab/icons/flags/) (or create your own 16x11 icon) and place it inside [`engine/src/main/resources/assets/textures/ui/icons`](https://github.com/MovingBlocks/Terasology/tree/develop/engine/src/main/resources/assets/textures/ui/icons). Rename it to `flag_xx.png`, `xx` being the two-letter code you've used before.

To submit the new translation,
  * `git commit ...`
  * `git push`
  * [Open a new pull request](https://github.com/MovingBlocks/Terasology/compare).

And while you're at it, feel free to add yourself to [Credits.md](https://github.com/MovingBlocks/Terasology/blob/develop/docs/Credits.md) as a new contributor!

***
Tutorial based on [@skaldarnar](https://github.com/skaldarnar)'s excellent [guide](https://github.com/MovingBlocks/TerasologyLauncher/wiki/Add-New-Translation) to translating the Terasology Launcher.