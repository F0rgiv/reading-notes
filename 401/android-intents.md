# Android Tasks, and SharedPreferences

## Tasks

Tasks are collections of activities that are interacted with by the user when performing a certain job. These activities are store in a stack that is accessible to the using by using the back button which will pop the most recent activity and remove the users current one.

## Shared Preferences

Like the saved keys value pairs within a file. They can also be access with R by going to ```R.string.preference_file_key```

These preferences can also easily be reed to and written from using the below methods

### Writing

Keys are added with ```putInt()``` and ```putString()```
Those are then save with ```apply``` or ```commit()```

    SharedPreferences sharedPref = 
        getActivity().getPreferences(Context.MODE_PRIVATE);
    SharedPreferences.Editor preffEditor = sharedPref.edit();


    preffEditor.putInt(getString(R.string.saved_high_score_key), newHighScore);
    preffEditor.apply();

### Reading

Similar to ```putInt()``` and ```putString()``` you can read the shared preferences with ```getInt()``` and ```getString()```

    SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);

    int defaultValue = getResources().getInteger(R.integer.saved_high_score_default_key);
    int highScore = sharedPref.getInt(getString(
        R.string.saved_high_score_key), defaultValue);