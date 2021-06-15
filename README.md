# test-akqa

The request of this sproject was to have a client has requested the implementation of a widget he wants to embed in different websites, and has provided some specifications that we need to follow.

• As a user visiting a site, I want to see a widget that, upon interaction, shows me a fun chuck Norris fact.

• The widget must be implemented as a pluggable wordpress widget and as a Drupal block that can be placed in any region of a theme (considering your existing Wordpress experience, try to give more
priority to the Drupal part, as it could result in a more challenging and interesting activity).

• The widget adapts its width based on the column that contains it.

• The widget uses the following REST API to get a rancom Chuck Norris quote: https://api.chucknorris.io/.
Use your creativity to use any of the fields contained in the API response, the only required one to be
used is “value”.

• The REST API can be queried either from the front-end (via JS) or from the back-end (server-to-server
call) upon your preference. The latter method is slightly more challenging and will be considered as an added value to the test.




DRUPAL BLOCK

I first divided the problem into two parts:
1. installation of the Drupal CMS and reading of the documentation for the creation of a custom block
2. development in html, css and javascript the API request

- to develop the part of the drupal block I used an additional module called "component" (https://www.drupal.org/project/component) which manages in a simpler way the CSS and JS files as well as the creation of an html template. To complete this development I followed the following steps:
  1. Write a simple module descriptor in drupal/modules/component/modules/component_example/components/component_test.info.yml to create a custom module
  2. Enable the module. Write a simple-ish component descriptor file in drupal/modules/component/modules/component_example/components/component_test/comp_test1.component.yml to create a new component block.
  3. Create component's body template in index.html
  4. Create component's JS file in script.js
  5. Create component's CSS file in style.ccs
  6. Upload the background image

- Regarding the management of the API, a script has been developed that uses the fetch API to make the JSON call




WORDPRESS WIDGET

You have two options to create a widget: develop it within the "functions.php" file of a WordPress theme or treat it as a plugin.
I used the second option in order to use it within any WordPress site.

The following steps explain the steps for creating the widget:
  1. Inside the plugins folder create the main plugin file /chucknorris/chucknorris.php
  2. Write the file /chucknorris/includes/chucknorris-scripts.php where JS and CSS files are added with a Wordpress function
  3. Write the file /chucknorris/includes/chucknorris-class.php where the API widget is developed
  4. Write the style.css file
  5. Write the script.js file

