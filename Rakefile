namespace :setup_javawrapper_build do
	task :copy_sdk_library do
		puts 'Copy sdk_library files from build_folder/lib/linix_x64 to vendor/lib'
	end

	task :copy_java_jni_files do
		puts 'Copied java_jni files from build_folder/wrapper/sdk_java/lib/linix_x64 to vendor/lib'
	end

	task :copy_java_swig_files do
		puts 'Copied java swig files from build_folder/wrapper/sdk_java/jar/ to vendor/jar'
	end

	task :copy_files_from_build => [:copy_sdk_library, :copy_java_jni_files, :copy_java_swig_files] 
end

task :default => 'setup_javawrapper_build:copy_files_from_build'




# Reference: 
# http://creedcultcode.blogspot.in/2011/02/rake-fundamentals-rakefiles-and-tasks.html
#
# A code block is a special Ruby construct that you can think of like an anonymous method or a lambda.  
# When you call a rake task, rake first executes all the prerequisite tasks you listed in the array in the first argument, 
# and then executes the code in the do…end code block.  If you only want to run prerequisite tasks without executing any 
# other code, just don’t include a do…end code block. 
#
# Thing to learn : How code blocks are used -> The function performs its prerequisite activity and then calls the 
#                  code block or lambda function.