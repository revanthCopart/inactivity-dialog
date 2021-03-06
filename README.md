# Inactivity Dialog

React Inactivity Validator Component based on Google's Material UI design with features to auto ok and auto cancel after certain timeout.

An example can be seen here: https://revanth0212.github.io/inactivity-dialog/

# Motivation

It is hard to keep track of keyboard events and mouse events when working on a shared document for instance which has a temporary lock on it in a multi user environment. This led to the Inactivity Validator Dialog. Also it has features like Auto OK or Auto Cancel (like in the Waze mobile application).

# Features

 1. Material UI
 2. Auto Ok / Auto Cancel (Like in case of Waze App)
 3. Check for Keyboard and Mouse Events to auto renew timer
 4. Heavily Customizable (both functionally and aesthetically)

# Installation

You can use npm or yarn.

    npm install inactivity-dialog

or

    yarn add inactivity-dialog

# Usage

Once done with the installation, you can get the component into your module using your favorite bundler/builder api. For instance,

    import InactivityDialog from 'inactivity-dialog'

or

    const InactivityDialog = require('inactivity-dialog')

# Props

|Name|Type|Default Value|Description|
|--|--|--|--|
| autoUnlockTimeout | number | 60 | Number of Seconds it takes for the timer to Auto OK / Cancel. |
| timeout | number | 180000 | Number of milliseconds of inactivity it takes for the dialog to come on to the screen. |
| beforeInactivityDialogOpen | function | () => {} | Function that will be called before the Inactivity Dialog shows up on the UI. |
| beforeInactivityDialogClose | function | () => {} | Function that will be called before the Inactivity Dialog moves away from the UI. |
| handleSubmit | function |() => {} | Function that will be called when the submit button is clicked (Right side button). |
| handleCancel | function | () => {}| Function that will be called when the cancel button is clicked (Left side button). |
| cancelButtonText | string | 'Cancel' | Text that needs to be shows on the cancel button. |
| submitButtonText | string | 'Submit' | Text that needs to be shown on the submit button. |
| userQuestion | string | 'Are you sure you want to submit?' | User question / message that needs to be shown on the dialog. |
| successfulMessage| string | 'Submitted sucessfully' | Successful message that needs to be shown on the dialog when the user clicks submit. |
|SuccessFulIcon | node | < LockOpen  color="green"  /> | The Icon that needs to be shown when the submit button is either clicked by user or auto clicked due to timer expiry. The default icon is a material ui icon taken from https://material.io/icons/.
|UserActionWaitingIcon| node | < LockOutline color="#0D5DB8"  /> | The Icon that needs to be shown when the dialog is opened and waiting for user action. The default icon is a material ui icon taken from https://material.io/icons/.
| buttonLabelStyle | object | { color: '#0D5DB8' } | CSS styling that will be applied on the Cancel and Submit button labels. |
| userActionWaitingColor | string | '#0D5DB8' | Color that will be used for the user question and timeout indicator. This will take precedence over color if provided in userQuestionStyle prop. |
| successfulActionColor | string | 'green' | Color that will be used for the successful message.  This will take precedence over color if provided in successfulMessageStyle prop.|
|userQuestionStyle|object|{}|Styling that will be applied on the User question component.|
|successfulMessageStyle|object|{}|Styling that will be applied on the Successful message component.|


# Example

    import  MuiThemeProvider  from  'material-ui/styles/MuiThemeProvider'
    
	import  InactivityDialog  from  'inactivity-dialog'
	
	<MuiThemeProvider>
    
	    <InactivityDialog
	    
		    handleSubmit={this.handleInactivityTimeoutSubmit}
		    
		    handleCancel={this.handleInactivityTimeoutCancel}
		    
		    timeout={10000}
		    
		    autoUnlockTimeout={60}
		    
		    beforeInactivityDialogOpen={this.beforeInactivityDialogOpen}
		    
		    beforeInactivityDialogClose={this.beforeInactivityDialogClose}
		    
		    cancelButtonText="No, Stay"
		    
		    submitButtonText="Yes, Leave"
		    
		    successfulMessage="Successfully auto clicked submit button."
		    
		    userQuestion="Do you want to perform certain action?"
	    
	    />
	    
    </MuiThemeProvider>

If you notice, we are wrapping the **InactivityDialog** component inside **MuiThemeProvider**. This is because the inactivity-dialog component uses material UI dialog component which needs the MuiThemeProvider to render.

**Make sure one of the parent component of Inactivity Dialog are wrapped inside the MuiThemeProvider.**

# Wanna Contribute?

This project is based on create-react-app. If you are familiar with the project structure and the module's goal, please branch out from master and create a PR once done.

Use 

    npm run start 

to start the local server. 

An example has been provided in 

> App.js

 file.