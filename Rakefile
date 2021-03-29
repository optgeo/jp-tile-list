require 'find'

SRC_DIR = "../fgd-adm/docs/zxy"

desc 'create the list'
task :list do
  w = File.open('list.csv', 'w')
  3.upto(16) {|z|
    Find.find("#{SRC_DIR}/#{z}") {|path|
      next unless /\/(\d*)\/(\d*)\.pbf$/.match path
      (x, y) = [$1, $2].map {|v| v.to_i}
      w.print [z, x, y].join(',') + "\n"
    }
  }
  w.close
end
