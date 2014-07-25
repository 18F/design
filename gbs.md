Graded Browser Support
--------------------------------
##Progressive enhancement
Our browser-support strategy is based entirely on the premise of “progressive enhancement”. Rather than having a list of supported and not-supported browsers, we start with all core content and behavior available in the HTML layer, which is supported by all browsers. Design, layout, and behaviors are then added in a progressive fashion for those browsers that support them well.

Key to this technique is the acceptance that webpages will not look and behave exactly the same in all browsers – a goal that is generally impossible in the modern landscape of varying screen sizes.

##Core content and functionality
All content and behavior should be available in base HTML.  Ensure forms submit without relying on Javascript, restrict CSS use to purely decorative purposes, and write elements that only use Javascript when Javascript is turned on.
The result is a web presence where our content is available to all site visitors, regardless of their device, browser, or assistive technology capabilities.

####Testing
Testing for core material can be performed in any browser by turning off CSS and Javascript, or by using something like a Lynx viewer. (http://www.delorie.com/web/lynxview.html)

##Basic CSS support
There are a number of browsers that attempted to support CSS, but generally failed to do so – for our purposes, these are primarily Netscape 4.x and Internet Explorer 5.x. These browsers, however, can render a somewhat basic but still branded stylesheet focusing on type and color (but, generally, with a single-column layout).

####Testing
As none of these browsers approaches 1% of our userbase, they can be limited to cursory testing except with reports of major bugs from users.

####Technical note
More-advanced stylesheets will be hidden from these browsers using the @import technique, which they do not implement.

##Enhanced CSS support
Internet Explorer versions 6, 7, and 8 have increasing support for CSS. They can support an experience increasingly similar to the full site experience. The level of support for these browsers begins with something not far beyond the basic CSS support explained above in the case of IE6, and extends to nearly full support with IE8.
IE7 falls somewhere in the middle, and will ultimately be a case-by-case decision based on resources, browser capabilities, and browser share (at the time of writing, it’s at about 12% for our last 30 days on a clear downward trend).

####Testing
Browser  Primary Test OS	Secondary Test OS
Internet Explorer 8	Windows 7	Windows XP
Internet Explorer 7	Windows XP	Windows Vista

Internet Explorer 6	Windows XP	N/A

####Technical note
Each of these browsers can be targeted with CSS (and Javascript) using conditional comments.

##Full support
The remaining browsers have strong support for most CSS 1 and 2 features, as well as some features of CSS 3. More importantly, they degrade gracefully by simply ignoring rules they don’t know how to implement. We can present an experience using items like rounded corners, transitions, and gradients while trusting browsers with limited support will ignore rules they can’t implement and still provide an excellent experience.

####Testing
Firefox, Chrome, and Safari all have auto-updating features and reliably have the vast majority of users on at least the second-most-recent release of the browser. Because of the combination of this fact with the graceful degradation principles discussed above, we can test only the two most-recent versions of these three browsers.
Additionally, there are niche browsers like Opera. These browsers generally have good support for web standards and have such tiny shares of our userbase that there is no need to test on them.

Browser  Primary Test OS	Secondary Test OS
Internet Explorer 9	Windows 7	Windows Vista
Firefox	Windows XP	Windows 7
Chrome	Windows XP	Windows 7

Safari	Mac OS X 10.7 Lion	Mac OS X 10.6 Snow Leopard
Mobile Safari	iOS 5	iOS 4
Android Browser	TBD	TBD
Internet Explorer 9 Mobile	Windows Phone 7.5 Mango	N/A

#Appendix
Examples of what works and doesn't work in certain browsers

##Accessibility - drop down menu
*For any drop down menus, a full list of all selections must be present at the bottom of the screen.
<insert image>

##Javascript forms
For any form created in Javascript, functionality must be written so that the form still works with Javascript turned off.

*1. Good Example: Know Befor You Owe student request.  The Ranking funtion in Step 2 works in Javascript and with Javascript disabled: http://www.consumerfinance.gov/students/knowbeforeyouowe/

*2. Bad example - Mortgage complaint form.  With Javascript disabled, the form does not work at all: https://help.consumerfinance.gov/app/mortgage/ask

*3. Bad example - Student loan repayment does not function without Javascript: http://www.consumerfinance.gov/students/repay/

##Layout 
As long as script does not harm functionality, it is OK to use Javascript.  If it will affect functionality, write code so that it can be applied without higher CSS and Javascript.

*1. Rounded corners on form elements: use square corners on forms; rounded corners do not appear on all browsers

*2. Gradients:

*3. Multiple backgrounds: