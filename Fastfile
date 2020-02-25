# This file contains the fastlane.tools configuration
# You can find the documentation at https://docs.fastlane.tools
#
# For a list of all available actions, check out
#
#     https://docs.fastlane.tools/actions
#
# For a list of all available plugins, check out
#
#     https://docs.fastlane.tools/plugins/available-plugins
#

# Uncomment the line if you want fastlane to automatically update itself
# update_fastlane

default_platform(:android)

platform :android do

  desc "Build Release"
  lane :build_release do 
    gradle(
      task: 'build',
      build_type: 'Release'
    )
  end

  desc "Deploy a new version to the Google Play"
  lane :deploy do |options|
    upload_to_play_store(
      track: options[:env],
      json_key_data: options[:key],
      apk: "app/build/outputs/apk/release/app-release.apk",
      skip_upload_images: "true", 
      skip_upload_screenshots: "true",
      skip_upload_metadata: "true" 
    )
  end
end
