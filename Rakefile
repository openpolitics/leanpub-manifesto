require 'yaml'

namespace :build do
  
  task :title_files do
    Dir.glob("manuscript/manifesto/*.md") do |filename|
      frontmatter = YAML.load_file(filename)
      if frontmatter["title"]
        File.open("manuscript/titles/#{File.basename(filename)}", "w") do |f|
          f.write("# #{frontmatter["title"]}")
        end
      end
    end
    
  end
  
end

task :default => :"build:title_files"