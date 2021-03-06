# Generating metadata for a specific chef version
- run 'bundle install' to install appraisal
- update Appraisals file with new chef version(s)
- run 'appraisal chef_12.7.2 bundle install' to generate the Gemfile and Gemfile.lock
- run 'appraisal chef_12.7.2 rake generate_chef_metadata' to generate json for that version of chef

# Generating metadata for all version of Chef
- run 'bundle install' to install appraisal
- update Appraisals file with new chef version(s)
- run 'appraisal' to generate the gemfiles for all the chef versions
- run 'appraisal rake generate_chef_metadata' to generate the json for all the chef versions

## Notes
The Rakefile is not intended to be run directly without invoking appraisal to essentially bundle exec it against the correct gemfile.

Due to incompatibility between legacy Chef releases and modern Ruby releases, generating metadata for all versions of Chef will fail. You'll need generate metadata for specific releases, or comment out the older releases in the Appraisal file before generating metadata in bulk.
