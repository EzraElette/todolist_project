require 'rake/testtask'
require 'find'
require 'bundler/gem_tasks'

desc 'Say Hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

task :default => [:test, :inventory]

Rake::TestTask.new(:test) do |t|
  t.libs << 'test'
  t.libs << 'lib'
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'List files'
task :inventory do
  Find.find('.') do |file|
    next if file.include?('/.')
    puts file if File.file?(file)
  end
end