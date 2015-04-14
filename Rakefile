require 'pathname'
require 'slim'

Slim::Engine.set_options pretty: true

index_slim   = Pathname.new 'index.slim'
index_html   = Pathname.new 'index.html'
lecture_slim = Pathname.new 'lecture.slim'

task :compile do
  layout   = Slim::Template.new(index_slim)   { index_slim.read   }
  template = Slim::Template.new(lecture_slim) { lecture_slim.read }

  index_html.write layout.render { template.render }
end

task default: :compile
