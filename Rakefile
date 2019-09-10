require 'active_record', "~>5.2.3"
include ActiveRecord::Tasks

DatabaseTasks.db_dir = 'db'
DatabaseTasks.migrations_paths = ['db/migrate']

load 'active_record/railties/databases.rake'

task :console => :environment do
  Pry.start
end

task :environment do
  require_relative 'config/environment'
end

Rake::Task["db:drop"].clear

namespace :db do
  task :drop => :environment do
    puts "Dropping tables"
    File.delete('db/schema.rb')
    drop_db
  end
end
