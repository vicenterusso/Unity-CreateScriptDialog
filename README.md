**Version 1.1 - for Unity 3.4 or higher**

Added Namespace support Based on "Create Script Dialog" from Unity Technologies

**Version 1.0 - for Unity 3.4 or higher**

# Create Script Dialog

By _Unity Technologies_ - [unity3d.com](http://unity3d.com)

## Using the Dialog

*   Open the dialog by choosing the menu <tt>Assets > Create > Script...</tt>.
*   Type a name for your new script in the Name field.
*   You can change the script type (JavaScript, CSharp, or Boo) if it's not set to the type you want.
*   Click a folder in the Project View to make the script be saved in that folder when it's created.
*   You can choose between different script templates. The default is always <tt>MonoBehaviour</tt>.
    *   If the <tt>MonoBehaviour</tt> template is used, you can click on a Game Object in the Hierarchy or Scene View to make the script be attached to that object when it's created.
    *   If the <tt>Custom Editor</tt> template is used, you can type in the name of the script you want to make a custom editor for.
    *   If the template supports functions, there is a Functions box where you can choose which functions you want to have included in the script from the beginning.
*   Click the <tt>Create</tt> button to create the script.

## Making Your Own Smart Template

If you have a certain type of script you often want to make, you can make your own smart template for it.

The script template is basically just a plain text file. The extension must be .js, .cs, or .boo. The name of the file will be used as the template name. The file must be placed in the folder <tt>Assets/CreateScriptDialog/SmartScriptTemplates</tt>.

Certain keywords can be used in the template to make it more smart.

``$ClassName``.
This will be replaced with the script name that is typed into the dialog.

``$NicifiedClassName``. This will be replaced with the script name that is typed into the dialog, but with added spaces. It can be used for naming menu items and such.

The template can specify what the base class for the script is by using the keyword ``BASECLASS`` in the first line of the template like this:
``BASECLASS=ClassNameOfBaseClass``

When a base class is specified, the dialog will look for a file called ClassNameOfBaseClass.functions and extract function data from there. Each line in the functions file must contain a valid function signature followed by a comment. For example:

``void LateUpdate() LateUpdate is called every frame, if the Behaviour is enabled.``

This can be prefixed with the keyword ``DEFAULT`` if the function should be included by default, e.g:

``DEFAULT void Update() Update is called every frame, if the MonoBehaviour is enabled.``

When a base class is specified in a template, some additional keywords can be used.

``$Functions``

All functions that are chosen in the dialog will be placed where this keyword is.

``$TargetClassName``

If the base class for the template script is ``Editor``, then this keyword will be replaced with the class name that is typed into the dialog in the field "Editor for".

## Contact

For questions or comments about the Create Script Dialog, please go to the [Unity Forums](http://forum.unity3d.com) or [UnityAnswers](http://answers.unity3d.com). If you don't get any useful replies within a few days, you can send me a private message on the forums (handle: runevision) and send me a link to the post you posted and I'll try to have a look.