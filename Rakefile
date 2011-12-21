require 'fileutils'

desc 'Links dotfiles and dirs in the home directory'
task :link do
  current_dir = FileUtils.pwd
  %w{vimrc gvimrc}.each do |file|
    FileUtils.ln_s("#{current_dir}/#{file}", "#{ENV["HOME"]}/.#{file}")
  end
  FileUtils.ln_s("#{current_dir}", "#{ENV["HOME"]}/.vim")
end

desc 'Build Command-T C-extension'
task :build_command_t do
  Dir.chdir('bundle/Command-T/ruby/command-t') do
    `ruby extconf.rb`
    `make`
  end
end
