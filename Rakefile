require "rake/testtask"
require "bundler/gem_tasks"
require "find"

desc "Say hello"
task :hello do
  puts "Hello there. This is the 'hello' task."
end


desc "Run tests"
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList["test/**/*_test.rb"]
end

desc "List all files"
task :list_files do
  Find.find(Dir.getwd) do |path|
    basename = File.basename(path)
    Find.prune if basename.start_with?(".")
    puts basename if File.file?(path)
  end
end