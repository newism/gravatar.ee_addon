_This is a Fork of https://github.com/philipzaengle/gravatar.ee\_addon which makes adding Gravatars as a submodule much easier._

### The EE Gravatar Plugin allows you to easily insert a "globally recognized avatar" image from Gravatar (http://www.gravatar.com/).

This plugin requires at a bare minimum one of two possible parameters depending on where you wish to use it. The first option is a user's email address {email} and the second option is a user's screen name {name}. The reason for this is so the plugin can be used in situations where one or the other parameter won't return the proper result. It is recommended that you use {email} for comment and entry loops and {name} for display in member profile templates, but feel free to experiment. Here's the two minimum required uses:

	<img src="{exp:gravatar email="{email}"}" /> -- For use in comment or entry loops.

	<img src="{exp:gravatar name="{name}"}" /> -- For use in templates such as Member Profiles where {email} won't work as expected.


## OPTIONAL PARAMETERS 

default="http://www.somesite.com/someimage.jpg"

Defines a default avatar if there isn't one associated with the email address or if it exceeds the rating.

rating="[G | PG | R | X]"

Allows you to limit gravatars to the appropriate rating. Anything exceeding the rating will use the default (if supplied) or not display.

size="[1..80]"

Allows you to define how big the gravatar will be in pixels. Any size other than 80 will cause the original gravatar image to be downsampled using bicubic resampling before output

## POSSIBLE EXAMPLES

Here's a few examples that you might use:

	<img src="{exp:gravatar email="{email}" rating="PG"}" />

Only displays gravatars of PG rating or lower.

	<img src="{exp:gravatar email="{email}" rating="R" size="40"}" />

Displays 40x40 pixel gravatars of R rating or lower.

	<img src="{exp:gravatar email="{email}" size="70" default="http://www.somesite.com/someimage.jpg"}" alt="Picture of {name}" title="{name}" class="avatar" />

Displays gravatars of 70x70 pixels or a default graphic for users without a gravatar. Puts the user's name in the alt and title tags and styles the image using a class called "avatar."

	<div class='profileTitle'><img src="{exp:gravatar name="{name}" size="80" rating="R"}" style="float: left; margin: 0; padding: 6px;" alt="{name} pic" title="{name}" />{name}</div>
	<p>{lang:member_group}&nbsp; <b>{member_group}</b></p>

The above is a snippet of code from my Public Member Profile template showing how to insert a gravatar into the member listings for your site.

## Credit
Current Developer: Philip Zaengle

Original Developer: Les Jenkins of http://stupidevilbastard.com/

## Change Log

v2.1 - Fixed a small security hole for users trying to use the name="" parameter incorrectly. 

v2.0 - Updated plugin to support the fantastic ExpressionEngine2.0 upgrade. Removed the border paramater, no longger documented or supported by gravatar. Adding precautions if someone a e-mail address is associated with the name value in the member profile.

V1.4 - Added {name} parameter as alternate to {email} for use in situations where {email} breaks the plugin such as Member Profiles.

V1.3 - Changed & to &amp; for XHTML validation compliance.

v1.2 - Made {email} into a parameter along for single tag usage for EE 1.1 release.

v1.1 - Minor bug fix.

v1.0 - Initial Release
