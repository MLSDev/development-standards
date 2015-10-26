# Android Coding Conventions

1. [Field Naming](#field-naming)
1. [Code Line Length](#code-line-length)
1. [If Statements](#if-statements)
1. [Indents](#indents)
1. [File Names](#file-names)
1. [Layout Elements Naming](#layout-elements-naming)
1. [Other](#other)


## Field Naming

* Non-public, non-static field names start with **m**.
* Static field names start with **s**.
* Other fields start with a lower case letter.
* Public static final fields (constants) are `ALL_CAPS_WITH_UNDERSCORES`.

For example:

```java
public class MyClass {
    public static final int SOME_CONSTANT = 42;
    public int publicField;
    private static MyClass sSingleton;
    int mPackagePrivate;
    private int mPrivate;
    protected int mProtected;
}
```

## Code Line Length

No more than 120 characters.


## If Statements

If-statement body may be written in a single line without braces (`{}`), if it is short:

```java
    // ...
    if (!mInstance) createInstance();
    // ...
```


## Indents

4 spaces or one Tab.


## File Names

### Icons

Use the prefix which describes the icon type.

* Icons
    * Prefix: `ic_`
    * Example: `ic_star.png`

* Launcher icons 
    * Prefix: `ic_launcher_`
    * Example: `ic_launcher_calendar.png`
    * _If there is only one launcher icon, you can simply name it_ `icon.png`

* Menu icons
    * Prefix: `ic_menu_`
    * Example: `ic_menu_archive.png`

* Status bar icons
    * Prefix: `ic_stat_sys_` or `ic_stat_notify_`
    * Example: `ic_stat_notify_msg.png`

* Tab icons
    * Prefix: `ic_tab_`
    * Example: `ic_tab_recent.png`
    * _Add state name if needed_: `pressed`, `default`, `selected` (e.g. `ic_tab_recent_pressed.png`)

* Dialog icon
    * Prefix: `ic_dialog_`
    * Example: `ic_dialog_info.png `
    

### Buttons

Example for button called _"name"_: 
* `bt_name_default.png` for default state
* `bt_name_pressed.png` for pressed state

Put XML (that defines the animation) to the `res/drawable/bt_name.xml` file.


### Layouts 

`dialog_name.xml`


### Graphic Assets

* Background: `bg_name.png`
* Image for `ImageView`: `im_name.png`
* Animations: 
    * keep animation definition files in `res/drawable` folder.
    * Buttons: `bt_name_anim.png`
    * Activity: `anim_name_of_activity_name_of_animation.png`

If there are lot of animations used in the app, put those in a `res/anim` folder.


## Layout Elements Naming

Example: 

```
android:id="@+id/rl_top_panel"
``` 

which means the element name is _"top panel"_, and its type is `RelativeLayout`.


## Other

In all other cases follow: 
* [Google Android Code Style Guidelines](http://source.android.com/source/code-style.html)
* [Oracle Java Code Conventions](http://www.oracle.com/technetwork/java/codeconventions-150003.pdf)
