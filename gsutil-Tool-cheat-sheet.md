
Gsutil is the command line tool used to manage buckets and objects on Google Storage.

# gsutil features:

-----------------
- ACLs: setting access control via Access Control Lists
- rsync: synchronizing folders and buckets
- lifeline: defining lifecycle rules
- signed urls: setting time limited online access ()
- perfdiag for troubleshooting
- logging, notifications and versioning

----------------

$ gsutil help
$ gsutil <command> help

# Now create a bucket named <bucketname>

$ gsutil mb gs://<bucketname>

#Use the gsutil mb command and a unique name to create a bucket:
gsutil mb -l us-east1 gs://my-awesome-bucket/


----------------

#Use the gsutil cp command to copy the image from the location where you saved it to the bucket you created:

gsutil cp Desktop/kitten.png gs://my-awesome-bucket

#Upload and download a file with cp
$ gsutil cp <local_file> gs://<bucketname>/
$ gsutil cp  gs://<bucketname>/<remote_file> ./

----------------
#Use the gsutil cp command to download the image you stored in your bucket to somewhere on your computer, such as the desktop:

gsutil cp gs://my-awesome-bucket/kitten.png Desktop/kitten2.png

----------------
#Use the gsutil cp command to create a folder and copy the image into it:

#transfer a file between buckets:
$ gsutil cp  gs://<bucket_A>/<remote_file> gs://<bucket_B>/

gsutil cp gs://my-awesome-bucket/kitten.png gs://my-awesome-bucket/just-a-folder/kitten3.png

----------------

# Create a folder in a bucket with cp
$ gsutil cp <new_folder> gs://<bucketname>/

# Upload a file to a <new_folder> with cp
$ gsutil cp <local_file> gs://<bucketname>/<new_folder>/

----------------
# List the folder with ls
$ gsutil ls gs://<bucketname>/

# Check storage space with du
$ gsutil du -h gs://<bucketname>/

----------------
# Use the gsutil ls command to list the contents at the top level of your bucket:

gsutil ls gs://my-awesome-bucket

----------------
# Use the gsutil ls command, with the -l flag to get some details about an object:

gsutil ls -l gs://my-awesome-bucket/kitten.png

----------------
# Use the gsutil acl ch command to grant all users read permission for the object stored in your bucket:

gsutil acl ch -u AllUsers:R gs://my-awesome-bucket/kitten.png

----------------
# To remove this permission, use the command:

gsutil acl ch -d AllUsers gs://my-awesome-bucket/kitten.png

----------------
# Use the gsutil i am ch command to give a specific email address permission to read and write objects in your bucket:

gsutil iam ch user:jane@gmail.com:objectCreator,objectViewer gs://my-awesome-bucket

----------------
# To remove this permission, use the command:

gsutil iam ch -d user:jane@gmail.com:objectCreator,objectViewer gs://my-awesome-bucket

----------------
# Use the gsutil rm command to delete an object:

gsutil rm gs://my-awesome-bucket/kitten.png

----------------
# Use the gsutil rm command with the -r flag to delete the bucket and anything inside of it:

gsutil rm -r gs://my-awesome-bucket

----------------
# Use the gsutil rm command with the -r flag to delete the bucket and anything inside of it:

gsutil rm -r gs://my-awesome-bucket

----------------






