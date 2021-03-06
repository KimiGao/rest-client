require 'rake'

require 'jeweler'

Jeweler::Tasks.new do |s|
	s.name = "rest-client"
	s.description = "A simple REST client for Ruby, inspired by the Sinatra microframework style of specifying actions: get, put, post, delete."
	s.summary = "Simple REST client for Ruby, inspired by microframework syntax for specifying actions."
	s.author = "Adam Wiggins"
	s.email = "adam@heroku.com"
	s.homepage = "http://rest-client.heroku.com/"
	s.rubyforge_project = "rest-client"
	s.has_rdoc = true
	s.files = FileList["[A-Z]*", "{bin,lib,spec}/**/*"]
	s.executables = %w(restclient)
end

Jeweler::RubyforgeTasks.new

############################

require 'spec/rake/spectask'

desc "Run all specs"
Spec::Rake::SpecTask.new('spec') do |t|
	t.spec_opts = ['--colour --format progress --loadby mtime --reverse']
	t.spec_files = FileList['spec/*_spec.rb']
end

desc "Print specdocs"
Spec::Rake::SpecTask.new(:doc) do |t|
	t.spec_opts = ["--format", "specdoc", "--dry-run"]
	t.spec_files = FileList['spec/*_spec.rb']
end

desc "Run all examples with RCov"
Spec::Rake::SpecTask.new('rcov') do |t|
	t.spec_files = FileList['spec/*_spec.rb']
	t.rcov = true
	t.rcov_opts = ['--exclude', 'examples']
end

task :default => :spec

############################

require 'rake/rdoctask'

Rake::RDocTask.new do |t|
	t.rdoc_dir = 'rdoc'
	t.title    = "rest-client, fetch RESTful resources effortlessly"
	t.options << '--line-numbers' << '--inline-source' << '-A cattr_accessor=object'
	t.options << '--charset' << 'utf-8'
	t.rdoc_files.include('README.rdoc')
	t.rdoc_files.include('lib/restclient.rb')
	t.rdoc_files.include('lib/restclient/*.rb')
end

