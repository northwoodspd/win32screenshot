require 'bundler'
Bundler::GemHelper.install_tasks

require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new(:spec)

RSpec::Core::RakeTask.new(:rcov) do |spec|
  spec.rcov = true
end

task :build => :spec
task :default => :spec
task "release:source_control_push" => :spec

require 'yard'
YARD::Rake::YardocTask.new

desc "Remove all temporary files"
task :clobber do
  rm_r ["spec/tmp", "doc", ".yardoc", "coverage"]
end

module Bundler
  class GemHelper

    # do not release to rubygems.org
    def rubygem_push(path)
      sh("gem push ./pkg/#{full_name} --host https://northwoodspd.jfrog.io/artifactory/api/gems/gems")
    end

    # skip the tag
    def tag_version
      return
    end
  end
end

def gem_helper
  @gem_helper ||= Bundler::GemHelper.new
end

def full_name
  "#{name}-#{version}.gem"
end

def name
  gem_helper.send(:name)
end

def version
  gem_helper.send(:version)
end