# mysql-travisci
Can Travis CI (re)start MySQL numerous times with non-dynamic parameters?

[![Build Status](https://travis-ci.com/knyrb/mysql-travisci.svg?branch=master)](https://travis-ci.com/knyrb/mysql-travisci)

Tip - after you add the repository, but before you upload the .travis.yml file into your github repository, go into your repository settings within travis:
 - profile -> repository settings cog-button thing on the right (no, the other right):
   - build only if .travis.yml is present? tick yes - allows you to keep travis at bay by deleting the yml file
   - auto-cancel branch builds? tick yes - worth it while you're sorting out your config, otherwise travis gets stuck on one build that will never be fixed if your .travis.yml file doesn't parse
 - looking at your repository in travis - more options three-bar drop-down menu thing top-right -> requests:
   - lists the actual instances where the github-travis integration signals a change in the yml - handy for figuring out if there's a parse error, or a build error
 - after the build finishes, 'view config' tab-thing to the right of 'job log':
   - shows you what the yml file winds up looking like as json
   - if you use any '{}' in your .travis.yml, it will cause errors in the resultant json - fix?

Todo:
 - avoid the ~80sec cache update at the end of the build - will unpacking mysql in the same way as for default data do the trick?
 - get the mysql .cnf files into git and use these on the fly, rather than generating them in the travis yml
