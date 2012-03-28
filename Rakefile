task :default => :build

desc 'Build the extension into a working bundle'
task :build do
  build_dir = "JSON Formatter.safariextension"

  FileUtils.rm_rf build_dir
  FileUtils.mkdir_p build_dir

  assets = [
    "etc/Info.plist",
    "etc/Settings.plist",
    "src/*"
  ]

  assets.each do |glob|
    Dir.glob(glob).each do |src|
      puts "linking #{src}"

      dest = "#{build_dir}/#{File.basename(src)}"
      FileUtils.mkdir_p File.dirname dest
      FileUtils.link src, dest
    end
  end

  puts <<-EOM

********************************************************
You can now use the Safari Extension Builder to compress
the bundle into a .safariextz for deployment.

A reminder for when I forget how to find the builder:
Safari > Develop > Show Extension Builder
********************************************************

  EOM
end
