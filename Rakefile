task :default => :build

desc 'Build the extension into a deployable bundle'
task :build do
  build_dir = "build/JSON Formatter.safariextension"

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
end
