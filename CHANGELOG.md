# sql_server Cookbook CHANGELOG

This file is used to list changes made in each version of the sql_server cookbook.

## Unreleased

## 6.2.1 - *2021-05-06*

## 6.2.0 - *2021-03-02*

- Sous Chefs Adoption
- Add proper InSpec tests
- Remove `windows_path` resource in client recipe as it's not needed anymore
- Set `netfx35_install` to false by default as it fails currently otherwise

## 6.1.0 (2020-06-24)

- Cookstyle 6.2.9 Fixes - [@xorimabot](https://github.com/xorimabot)
- Standardise files with files in chef-cookbooks/repo-management - [@xorimabot](https://github.com/xorimabot)
- [GH-146] SQL 2019 Support

## 6.0.0 (2020-02-19)

This release removes support for deprecated SQL Server, Chef Infra Client, and Windows OS releases:

- Require Chef Infra Client 13+
- Remove support for Windows 2008 R2
- Remove support for SQL Server 2008 and 2014

## 5.6.0 (2020-02-18)

- Resolve multiple Cookstyle warnings - [@tas50](https://github.com/tas50)
- Remove unused long_description metadata - [@tas50](https://github.com/tas50)
- Remove unnecessary foodcritic comments - [@tas50](https://github.com/tas50)
- Remove windows 2008 r2 specs - [@tas50](https://github.com/tas50)
- Fix to install SQL on any custom directory - [@bhavya5491](https://github.com/bhavya5491)
- Require Chef 12.15+ - [@tas50](https://github.com/tas50)
- Updated checksum for 2008R2 - [@kenlangdon](https://github.com/kenlangdon)

## 5.5.1 (2019-06-05)

- Example resources should not have backticks but single quotes - [@gsreynolds](https://github.com/gsreynolds)
- Added the ability to override ASSVCACCOUNT in the Configuration File - [@jcurcio](https://github.com/jcurcio)

## 5.5.0 (2018-02-10)

- Add property to make .Net 3.5 install optional

## 5.4.1 (2018-01-10)

- Fix .kitchen.yml file for chef 12.7 testing
- Fix typo with sysadmins property
- Fix feature_list property in ConfigurationFile.ini

## 5.4.0 (2018-01-03)

- Add `install` custom resource that installs the specified version of SQL Server
- Add `configure` custom resource that configures SQL ports and services
- Bump minimum chef version to 12.7
- Update readme to support new resources (#92)
- Add support of SQL 2017 to the resource
- Add support to all features to custom resources
- Recommend wrapper cookbook over backwards compatible recipes
- Update licensing for the new year

## 5.3.2 (2017-10-14)

- Change default version to 2012 in the readme
- Remove maintainer files and add info to the readme
- Clarifies password in the readme
- Clean up broken link in README

## 5.3.1 (2017-03-27)

- Update windows cookbook dependency to 3.0.0 due to changes to windows_feature resource. (#89)
- Fix reboot post install logic. (#90)

## 5.3.0 (2017-03-17)

- Update SQL 2016 Express URL to SP1 and update readme to reflect support for 2016. (#88)

## 5.2.1 (2017-03-08)

- Add appveyer integration testing of the client recipe and remove Travis CI testing (#86)

## 5.2.0 (2017-03-07)

- Test with Local Delivery instead of Rake
- Fix failures on Windows 2008r2 by installing NetFx3 if necessary

## 5.1.2 (2017-01-31)

- Fix issue with Deprecation:Some Attribute Methods (CHEF-4) error

## 5.1.1 (2017-01-16)

- Only start and enable agent if agent_startup is set to automatic

## 5.1.0 (2016-12-20)

- Move server configuration in a new `sql_server::configure` recipe
- Add attributes to control network listeners via registry keys.

## 5.0.0 (2016-11-22)

- Avoid deprecation warnings with `windows_package` by using package instead. This requires Chef 12.6+ and Windows cookbook 2.0+
- Adding support for SQL Server Version 2014
- Default to SQL Server 2012
- Move a good chunk of the version logic to helpers instead of doing it in the recipes
- Use secure links to download older SQL express releases
- Add basic sql express 2016 support
- Don’t fail if the SQL version specified is an int and not a string
- Avoid blank lines if the optional configs aren’t passed

## 4.0.0 (2016-11-18)

- Remove relation between client & server recipes. This was not working correctly. You'll want to include both if you want client packages on your server now.
- Added Filestream Support
- Improved password escaping
- Remove SQL Server 2008 R2 / 2008 R2 SP1\. You must now be using 2008 R2 SP2+

## 3.0.0 (2016-09-07)

- Correct attribute to accept eula
- Require Chef 12+
- Testing updates

## v2.6.2(2016-05-17)

- README updates

## v2.6.1(2016-05-17)

- [PR #69](https://github.com/chef-cookbooks/sql_server/pull/69) Duplicate service restart
- Clean up rake file, maintainers toml/markdown

## v2.6.0(2016-05-17)

- [PR #59](https://github.com/chef-cookbooks/sql_server/pull/59) Support Named Instances
- [PR #61](https://github.com/chef-cookbooks/sql_server/pull/61) Restart Command For SQL Server
- [PR #67](https://github.com/chef-cookbooks/sql_server/pull/67) Updates for Standard Edition
- [PR #68](https://github.com/chef-cookbooks/sql_server/pull/68) Clarify remote install note

## v2.5.0(2016-02-12)

- Enable multiple sysadmin names.
- Removed the logic that auto generated node['sql_server']['server_sa_password'] and saved it to the node. The user will now need to set this to use the server recipe
- Removed the gem install of tiny_tds. This is not directly used by this cookbook. If you require this for the database cookbook you should install it in your own wrapper cookbook.
- Added support for SQL Server Client 2008 R2 SP2/SP2 and 2012 package installation
- Added the ability to specify the directories for system dbs, user dbs, logs, and tempdb in ConfigurationFile.ini
- Removed assumptions that C: is your system drive
- Added support SQL 2014 server in ConfigurationFile.ini
- Added the ability to pass account passwords to the installer vs. placing them in ConfigurationFile.ini
- Added ability to configure tempdb path, sqlbackupdir path, and sqlcollation in ConfigurationFile.ini
- Fixed computation of the reg_version and service_name variables
- Clarified the system and chef requirements in the readme
- Removed the Berksfile.lock
- Added Test Kitchen config with client and server suite
- Added updated contributing and testing docs
- Added Travis config
- Added Rakefile for simplified testing
- Added Rubocop config and resolved all warnings
- Added Gemfile with testing deps
- Added Maintainers files
- Added travis and cookbook version badges to the readme
- Added source_url and issues_url metadata for Supermarket

## v2.4.0 (2014-08-13)

- Fixing Checksums
- Changes to attribute interface

## v2.2.3 (2014-02-18)

- reverting OpenSSL module namespace change

## v2.2.2 (2014-02-17)

- updating to use the latest openssl

## v2.2.0 (2014-03-27)

- [COOK-4355] - Fix support for SQL server by using the right registry path

## v2.0.0 (2014-02-27)

[COOK-4253] - Make install options configurable

## v1.4.4 (2014-02-21)

### Improvement

- **[COOK-4268](https://tickets.chef.io/browse/COOK-4268)** - sql_server does not support installing SQL 2012

## v1.4.1 (2014-02-21)

### Improvement

- **[COOK-3892](https://tickets.chef.io/browse/COOK-3892)** - sql_server cookbook uses deprecated windows_registry LWRP

### Bug

- **[COOK-3725](https://tickets.chef.io/browse/COOK-3725)** - sql_server randomly-generated SA password sometimes not strong enough

## v1.3.0

### Improvement

- **[COOK-3507](https://tickets.chef.io/browse/COOK-3507)** - Broken SQLExpress download links...

### Bug

- **[COOK-3506](https://tickets.chef.io/browse/COOK-3506)** - SQLEXPRESS on 32 bits systems does not support INSTALLSHAREDWOWDIR
- **[COOK-3388](https://tickets.chef.io/browse/COOK-3388)** - Mixlib::ShellOut::CommandTimeout: command timed out error

## v1.2.2

- See (v1.2.1), made a mistake with DevOdd releases

## v1.2.1

### Improvement

- **[COOK-3088](https://tickets.chef.io/browse/COOK-3088)** - Allow setting feature_list

## v1.2.0

### Bug

- [COOK-3085]: Sql server configuration is incorrect when trying to install non-express version

## v1.1.0

- [COOK-1049] - remove unneeded external restart script from sql_server::server recipe

## v1.0.4

- bump windows cookbook dependency version to pick up Ruby 1.9 compat fixes

## v1.0.2

- [COOK-773] win_friendly_path is no longer a module_function
- rename accept_license_terms attribute to accept_eula for consistency with other cookbooks like iis

## v1.0.0

- [COOK-681] initial release
