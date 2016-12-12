set :stage, :production
set :rails_env, 'production'
server 'EC2のElasticIP', user: 'EC2で作成したユーザー名(rootのユーザー。Mysqlとは違うよ)', 
roles: %w{web app db}  #何サーバーの処理を書くか。今回は同じサーバーで全部動かすのでweb app db全て指定
#sshでEC２に入るのに必要
set :ssh_options, {
   keys: [File.expand_path('~/.ssh/EC2で任意でつけてダウンロードしたキー名.pem)')]
}
