# # -*- ruby -*-

# require "rubygems"
# require "hoe"

# # Hoe.plugin :compiler
# # Hoe.plugin :gem_prelude_sucks
# # Hoe.plugin :inline
# # Hoe.plugin :minitest
# # Hoe.plugin :racc
# # Hoe.plugin :rcov
# # Hoe.plugin :rdoc

# Hoe.spec "stree" do
#   # HEY! If you fill these out in ~/.hoe_template/default/Rakefile.erb then
#   # you'll never have to touch them again!
#   # (delete this comment too, of course)

#   # developer("FIX", "FIX@example.com")

#   # license "MIT" # this should match the license in the README
# end

# # vim: syntax=ruby


require 'rubygems'
require 'hoe'
require "rake/extensiontask"

HOE = Hoe.spec 'stree' do
  developer('Aaron Patterson', 'aaron@tenderlovemaking.com')
  self.readme_file   = 'README.txt'
  self.history_file  = 'History.txt'
  self.extra_rdoc_files  = FileList['*.rdoc']
  self.extra_dev_deps << ['rake-compiler', '>= 0']
  self.spec_extras = { :extensions => ["ext/stree/extconf.rb"] }
end

Rake::ExtensionTask.new(HOE.name, HOE.spec) do |ext|
  ext.lib_dir = File.join('lib', 'stree')
end

Rake::Task[:test].prerequisites << :compile
