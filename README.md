# Lucky_number

## Working:
This application will ask the user to enter his/her name. Then the user have to press button "wish me a luck", then we will be directed to another activity generating a random number

This application will allow the user to share the result among other applications that are available on the device.
we can copy and share to e-mail, Bluetooth, Goodle drive and other application.

## What we will learn ?
• In this application we will learn how to get the data from the edit text.

• How to pass the data among the intents.

• How to paas and share that data among other applications, using "Implicit intent" & "Explicit intents"

## Step 1: Set Layout for MainActivity

### 1) Go to "acitvity_main.xml" create TextView
This View will display the text on the screen when you open application

• set layout width and height to wrap_content.

• set id.

• Set android text.

• set layout margin if needed.

• Then finally click set all constrains.

### 2) Similarly create EditText View: 
This View will allow user to Enter their name

• To showcase what user have to enter, set hint = "Enter your name"
  Next all process is similar to Textview

### 3) Now to Create a Button

  • This Button will take user to the secondActivity.
  
  • set Button id.
  
  • set button text.

### 4) Now to set the Background image of application:
Download, copy and past images in res > drawable folder

After downloading go to the top of the page and under the layout width and layout height add background attribute and track location of "res" folder

Now create Image View.
Process is similar to TextView, EditText and Button.

## Step 2: process of Creating the Second Activity is similar to First:
• Create a TextView to display the text

• Create another TextView to display Numbers.

• Create a Button to share the Number to other applications.

## Step 3:
**Lets initialise the widgets of the MainActivity and add the functionality of
"Wish me a Luck" that allows the user to be directed second Activity**

### 1) Declaring the widget:

    EditText editText;
      
    Button btn;
      
    TextView txt;

### 2) After decalring the widget we initialise them in @Override "onCreate" method:

      @Override
          protected void onCreate(Bundle savedInstanceState) {
              super.onCreate(savedInstanceState);
              setContentView(R.layout.activity_main);
      
              // Initialising the Widgets:
              txt = findViewById(R.id.textView);
              editText = findViewById(R.id.edit_text);
              btn = findViewById(R.id.btn);
          }
### 3) Now we add functionality to button. So to add the funcitonality we will use ClickListner:
      btn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

            }
        });
**Here we need to direct the user to the second activity, but i need to get the name of the user
from the "EditText" and pass it to the second activity**

### 4) we get the username and we will store it inside the "userName" String variable
    String userName = editText.getText().toString();
### 5) Now we will use "Explicit Intent" 
    Intent i = new Intent()
Because we are navigating between the components of the same applicaiton, and we will pass 2 parameters "this" & "SecondActivity".


**This will give error because "this" is not refered to a context.
So we need to pass a context package content.
i.putExtra()**


**The putExtra() method is used to include additional data within an intent object.
This data will pass along with the intent and can be retrieved by the receiving component**

    getApplicationContext(),
                        SecondActivity.class
                        **
This will return context variable**
