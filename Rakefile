# frozen_string_literal: true
namespace :bookmarks do
  desc 'update bookmarks'
  task :update do
    sh('rm -rf bkmrq*.md README.md')
    sh('bkmrq -B brave')
    sh('mv bkmrq*.md README.md')
    sh("cp /home/#{ENV['USER']}/.config/BraveSoftware/Brave-Browser/Default/Bookmarks ./marks")
    sh("git add . && git commit -m \"[#{Time.now}] Bookmarks Updated\" && git push")
  end
end
