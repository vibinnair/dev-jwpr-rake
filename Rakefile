namespace :setup_javawrapper_build do
	SOURCE_BUILD_DIR      = '/home/test/Vibin/Workarea/Projects/builds'
 	SOURCE_BUILD_NAME      = 'xxxx'
 	SOURCE_BUILD_PLATFORM  = 'xxxx'
 	SOURCE_FILE_NAME       = '*.so.*'
    SDK_LIBRARY_FILES      = File.join(SOURCE_BUILD_DIR, SOURCE_BUILD_NAME, 'lib', SOURCE_BUILD_PLATFORM, '*.so.*')   


    TARGET_DIR = 'Test/xxxx/xxxx'
    TARGET_DIR_PATH = File.join('/home/test/Vibin/Workarea/Research/', TARGET_DIR)

    desc "Create test directory"
    directory TARGET_DIR_PATH
  	
  	desc "Copy sdk_library files from build_folder/lib/linix_x64 to vendor/lib" # Everything mentioned in prerequisite is called 
	FileList[SDK_LIBRARY_FILES].each do |source_file|	
		target_file = File.join(TARGET_DIR_PATH, File.basename(source_file))
		
		file target_file => [TARGET_DIR_PATH] do |t|							   		   
			cp source_file, target_file					           
		end                                                        
																   
	 	task :copy_sdk_library => [target_file]
	 end                                                                            
	 
	 task :copy_files_from_build => [:copy_sdk_library] 
end

task :default => 'setup_javawrapper_build:copy_files_from_build'