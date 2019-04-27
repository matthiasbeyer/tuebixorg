require "html-proofer"

task default: %w[test]

desc "Test the HTML files"
task :test do
  options = {
    :alt_ignore => [/.*/],
    :url_ignore => [/^http:\/\/tuebix2015\.titanpad\.com/,/^\.\.\/2015\/programm\//,/^(#)$/],
    :file_ignore => [/^_site\/201[5-7]\//],
    :typhoeus => {
      :followlocation => true,
      :connecttimeout => 300,
      :timeout => 600,
      :ssl_verifypeer => false,
      :ssl_verifyhost => 0
    },
    :only_4xx => true,
  }
  HTMLProofer.check_directory("_site", options).run
end
