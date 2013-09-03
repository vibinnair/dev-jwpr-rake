namespace :setup_javawrapper_build do
	task :copy_gnsdk_library do
		puts 'Copy gnsdk_library files from build_folder/lib/linix_x64 to vendor/lib'
	end

	task :copy_java_jni_files do
		puts 'Copied java_jni files from build_folder/wrapper/gnsdk_java/lib/linix_x64 to vendor/lib'
	end

	task :copy_java_swig_files do
		puts 'Copied java swig files from build_folder/wrapper/gnsdk_java/jar/ to vendor/jar'
	end

	task :copy_files_from_build => [:copy_gnsdk_library, :copy_java_jni_files, :copy_java_swig_files] 
end

task :default => 'setup_javawrapper_build:copy_files_from_build'