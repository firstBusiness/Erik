# Uncomment this line to define a global platform for your project

use_frameworks!
inhibit_all_warnings!
# compute_swift_version_from_targets!

def dependency_pods
    # pod 'Result', :git => 'http://github.com/antitypical/Result.git', :branch => 'master'
    pod 'Kanna', :git => 'http://github.com/tid-kijyun/Kanna.git', :branch => 'swift3.0'
    pod 'BrightFutures', :git => 'http://github.com/oysta/BrightFutures.git', :branch => 'xcode8b6'
end

def testing_pods
    dependency_pods
    pod 'FileKit', :git => 'http://github.com/nvzqz/FileKit.git', :branch => 'develop'
end

target 'Erik' do
    platform :ios, '9.0'
    dependency_pods
end

target 'ErikTests' do
    platform :ios, '9.0'
    testing_pods
end

target 'ErikOSX' do
    platform :osx, '10.10'
    dependency_pods
end

target 'ErikOSXTests' do
    platform :osx, '10.10'
    testing_pods
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['SWIFT_VERSION'] = '3.0'
    end
  end
end
