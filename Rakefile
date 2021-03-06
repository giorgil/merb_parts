require 'rubygems'
require 'rake'

# Assume a typical dev checkout to fetch the current merb-core version
require File.expand_path('../../merb/merb-core/lib/merb-core/version', __FILE__)

# Load this library's version information
require File.expand_path('../lib/merb_parts/version', __FILE__)

begin

  require 'jeweler'

  Jeweler::Tasks.new do |gemspec|

    gemspec.version     = Merb::Parts::VERSION

    gemspec.name        = "merb_parts"
    gemspec.description = "Merb plugin that provides Part Controllers."
    gemspec.summary     = "Merb plugin that provides Part Controllers."

    gemspec.authors     = [ "Daniel Neighman" ]
    gemspec.email       = "has.sox@gmail.com"
    gemspec.homepage    = "http://github.com/merb/merb_parts"

    gemspec.files       = %w(CHANGELOG LICENSE Rakefile README TODO) + Dir['{lib,spec}/**/*']

    # Runtime dependencies
    gemspec.add_dependency 'merb-core',     ">= 0.9.9"

    # Development dependencies
    gemspec.add_development_dependency 'rspec', '>= 1.2.9'

  end

  Jeweler::GemcutterTasks.new

rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'spec/rake/spectask'
Spec::Rake::SpecTask.new(:spec) do |spec|
  spec.spec_opts << '--options' << 'spec/spec.opts' if File.exists?('spec/spec.opts')
  spec.libs << 'lib' << 'spec'
  spec.spec_files = FileList['spec/**/*_spec.rb']
end

Spec::Rake::SpecTask.new(:rcov) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end

desc 'Default: run spec examples'
task :default => 'spec'
