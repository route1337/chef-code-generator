Deprecated Repo
------------
Route 1337, LLC's Chef repos have been deprecated and will no longer be supported. We are happy to take community contributions or invite volunteer maintainers if support is desired. If you wish to maintain our Chef repos you may [contact us](https://www.route1337.com/contact-us/).

Route 1337 Chef Code Generator Template
==============
This repo contains the standard Route 1337, LLC cookbook template for creating Chef cookbooks with the `chef generate` command

Requirements
------------
1. ChefDK (Tested on 2.4.17-1 for macOS

Installation Tips
------------

1. I personally keep this checkout in `~/Chef/Route1337/pan`

Limitations
------------
1. None so far :)

Known Issues
------------
1. `.chef/config.rb` must have all of the variables from `.chef/knife.rb` added to it or knife commands will break when trying to interact with the server

Bug Fixes & Changes
------------

1. v0.1.6
    1. Adding testing for Ubuntu 18.04
2. v0.1.5
    1. Setting 13.6.4 as the minimum supported Chef version but allowing greater versions again
3. v0.1.4
    1. Fixing a mistake in the Chef version supported by the generated metadata.rb
4. v0.1.3
    1. Fixing generated README.md to reflect tested Chef version
5. v0.1.2
    1. Locking test kitchen to Route 1337's accepted chef-client version of 13.6.4
6. v0.1.1
    1. Fixing generated documentation in order to align with Foodcritic expectations
7. v0.1.0
    1. Initial release

Configuration & Use
------------
There are a few simple steps to configure this template

1. Check the repo out to a path of your choice
2. Configure your .chef/config.rb as follows (Route 1337 always uses the MIT license)
    ```
    if defined?(ChefDK)
      chefdk.generator.copyright_holder "Joe Developer"
      chefdk.generator.license   "mit"
      chefdk.generator.email     "joe.developer@route1337.com"
      chefdk.generator_cookbook  "/Users/joedeveloper/Chef/Route1337/chef-code-generator/code_generator"
    end
    ```
    1. If you have a knife.rb make sure those variables are ported to config.rb as well or knife will break. Example:
    ```
    if defined?(ChefDK)
      chefdk.generator.copyright_holder "Joe Developer"
      chefdk.generator.license   "mit"
      chefdk.generator.email     "joe.developer@route1337.com"
      chefdk.generator_cookbook  "/Users/joedeveloper/Chef/Route1337/chef-code-generator/code_generator"
    end
    node_name                'joedeveloper'
    client_key               '/Users/joedeveloper/Chef/Route1337/.chef/joedeveloper.pem'
    validation_client_name   'route1337-validator'
    validation_key           '/Users/joedeveloper/Chef/Route1337/.chef/route1337_org.pem'
    chef_server_url          'https://chefserver.route1337.com/organizations/route1337'
    cookbook_path            ["/Users/joedeveloper/Chef/Route1337/Cookbooks"]
    ```
3. You can now create cookbooks using the template via `chef generate cookbook $cookbookName`
