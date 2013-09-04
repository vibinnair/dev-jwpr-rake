namespace :setup_javawrapper_build do
	SOURCE_BUILD_DIR      = '/home/test/Vibin/Workarea/Projects/builds'
 	SOURCE_BUILD_NAME      = 'gnsdk-3.06.0.1071-20130822'
 	SOURCE_BUILD_PLATFORM  = 'linux_x86-64'
 	SOURCE_FILE_NAME       = 'libgnsdk_correlates.so.3.06.0'
    SOURCE_INPUT_FILE_PATH = File.join(SOURCE_BUILD_DIR, SOURCE_BUILD_NAME, 'lib', SOURCE_BUILD_PLATFORM, SOURCE_FILE_NAME)   


    TARGET_DIR = 'Test'
    TARGET_DIR_PATH = File.join('/home/test/Vibin/Workarea/Research/', TARGET_DIR)

    desc "Create test directory"
    directory TARGET_DIR_PATH
  

	desc "Copy sdk_library files from build_folder/lib/linix_x64 to vendor/lib"
	file "libgnsdk_correlates.so.3.06.0" => [TARGET_DIR_PATH, SOURCE_INPUT_FILE_PATH] do |t| 
		cp SOURCE_INPUT_FILE_PATH, File.join(TARGET_DIR_PATH, t.name)
	end

	task :copy_sdk_library => ['libgnsdk_correlates.so.3.06.0'] # How to call a file task from MartinFowler

	#task :copy_java_jni_files do
	#	puts 'Copied java_jni files from build_folder/wrapper/sdk_java/lib/linix_x64 to vendor/lib'
	#end

	#task :copy_java_swig_files do
	#	puts 'Copied java swig files from build_folder/wrapper/sdk_java/jar/ to vendor/jar'
	#end

	task :copy_files_from_build => [:copy_sdk_library] 
	#task :copy_files_from_build => [:copy_sdk_library, :copy_java_jni_files, :copy_java_swig_files] 
end

task :default => 'setup_javawrapper_build:copy_files_from_build'


# TODO:
# 1. Expand task to read all files from the folder and paste it to test. (Refer MArtin Fowler and FileList 
#    in http://docs.rubyrake.org/user_guide/chapter03.html)


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


# File task
# ----------
# Syntax:
# file "What to create" => "How to create" (This includes input file names in prerequisites and the process of making it 
#											in the code block).
# 
# Sample: 
# file 'hello.txt' => [list of prerequisites] do |task_object| 
#       task_object.prerequisites[parameter_no] --> using the task object you can access the passed prerequisites array. 
#       task_object.name -->  using the task object you can access the name of the output file by calling "task_object.name".  
# end
#
#
#
#
# References: 
# http://martinfowler.com/articles/rake.html#FileTasks (The above concept is explained here).
# http://creedcultcode.blogspot.in/2011/03/rake-fundamentals-file-tasks.html (The above concept is shown here).
# http://www.ibm.com/developerworks/opensource/tutorials/os-rubyrake/section3.html