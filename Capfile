###
# Upload the data to an EBS volume and snapshot it.

require 'catpaws'

#generic settings
set :aws_access_key,  ENV['AMAZON_ACCESS_KEY']
set :aws_secret_access_key , ENV['AMAZON_SECRET_ACCESS_KEY']
set :ec2_url, ENV['EC2_URL']
set :ssh_options, { :user => "ubuntu", :keys=>[ENV['EC2_KEYFILE']]}
set :key, ENV['EC2_KEY']
set :key_file, ENV['EC2_KEYFILE']
set :ami, 'ami-7e5c690a' #32-bit Ubuntu Maverick, eu-west-1
set :instance_type, 'm1.small'
set :working_dir, '/mnt/work'
set :availability_zone, 'eu-west-1a'  
set :nhosts, 1
set :group_name, 'clores_vs_florescre_rnaseq'
set :snap_id, `cat SNAPID`.chomp #ec2 eu-west-1 
set :vol_id, `cat VOLUMEID`.chomp #empty until you've created a new volume
set :ebs_size, 250 
set :dev, '/dev/sdf'
set :mount_point, '/mnt/data'



#make a new EBS volume from this snap 
#cap EBS:create

#and mount your EBS
#cap EBS:attach
#cap EBS:format_xfs
#cap EBS:mount_xfs

before 'install_samtools', 'EC2:start'

desc "install samtools"
task :install_samtools, :roles => group_name do
  sudo "apt-get update"
  sudo "apt-get -y install samtools"
end 



# cap EBS:snapshot
# cap EBS:unmount
# cap EBS:detach
# cap EBS:delete 
# cap EC2:stop

