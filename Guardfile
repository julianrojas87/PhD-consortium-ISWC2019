guard :nanoc do
  watch 'nanoc.yaml'
  watch 'Rules'
  watch %r{^(content|layouts|lib)/}
end

guard :process, name: 'server', command: 'bundle exec serve' do
  watch 'Gemfile.lock'
end

guard :livereload do
  watch(%r{^docs/}) { |m| m[0].sub(%r{^docs/}, '') }
end

notification :notifu, :nosound => true