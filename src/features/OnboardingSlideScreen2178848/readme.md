# CB Slide Onboarding Tutorial Screen

The CB Slide Onboarding Tutorial Screen is a ReactNative based onboarding screen. It can be configured to have 1 or many 
slide screens with content and expansion detailed in the file.
  
## Installation

After you have added the screen module into your project, you will need to configure a few items by modifying the project 
files in the github repository. You will need to review/modify/add:

  ADD Dependency after Line 16 (dependencies opening line) in /PROJECT_ROOT_DIRECTORY/package.json
      "react-native-app-intro-slider": "^4.0.4",

  MODIFY Line 44 in screen_folder/index.js
      Replace with your features/screen_folder name

 /src/features/SplashScreen######/navigator.js (where the ##### is replaced by the generated numeric string specific to your 
  project)
    ADD after Line 10
      '''code   defaultNavigationOptions: ({ navigation }) => ({ header: null }), '''
  
  REVIEW /src/config/installed_blueprints.js
    Make sure any screens that aren’t desired in the side menu are removed from the file.

    In installed_blueprints.js you need to add objects for every screen that you want to show in the sidemenu/splash screen.
    They have a specific format:
    '''code { name: 'login', human_name: 'Sign In', access_route: 'Login'} '''
            name - doesn't matter much, its used as a unique key for the side menu and splash screens array of 
                 buttons - it must be unique, that's the only requirement
            human_name - is what will be displayed in actual app
            access_route - must be the name of the key in your mainNavigator setup  
  
  /src/mainNavigator.js
    ADD comma in Line 44 (IMPORT_SCREEN_NAME must match the access_route in the installed_blueprints.js file above)
     '''code   (contentComponent: SideMenu , '''
    ADD After Line 44 (this RouteName must match the name in the installed_blueprint.js file)
     '''code   initialRouteName: “IMPORT_SCREEN_NAME”, '''

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)