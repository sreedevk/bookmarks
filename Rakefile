# frozen_string_literal: true

namespace :bookmarks do
  desc 'generate bookmarks (no push)'
  task :generate do
    sh('rm -rf bkmrq*.md README.md raw-bookmarks.json')
    sh('bkmrq -b brave -f markdown -o README.md')
    sh("cp /home/#{ENV['USER']}/.config/BraveSoftware/Brave-Browser/Default/Bookmarks ./raw-bookmarks.json")
  end

  desc 'update bookmarks'
  task :update do
    Rake::Task['bookmarks:generate'].invoke
    sh("git add . && git commit -m \"[#{Time.now}] Bookmarks Updated\" && git push")
  end
end
