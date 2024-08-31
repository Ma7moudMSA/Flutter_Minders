
```

import 'package:flutter/material.dart';  
  
void main() {  
  runApp(const MyApp());  
}  
  
class MyApp extends StatelessWidget {  
  const MyApp({super.key});  
  
  @override  
  Widget build(BuildContext context) {  
    return MaterialApp(  
      title: 'Create Account',  
      theme: ThemeData(  
        primarySwatch: Colors.blue,  
      ),  
      home: const LoginPage(),  
    );  
  }  
}  
  
class LoginPage extends StatefulWidget {  
  const LoginPage({super.key});  
  
  @override  
  _LoginPageState createState() => _LoginPageState();  
}  
  
class _LoginPageState extends State<LoginPage> {  
  final _formKey = GlobalKey<FormState>();  
  final TextEditingController _passwordController = TextEditingController();  
  final TextEditingController _confirmPasswordController =  
      TextEditingController();  
  
  @override  
  Widget build(BuildContext context) {  
    return Container(  
      decoration: const BoxDecoration(  
        gradient: LinearGradient(  
          colors: [Color(0xFF252035), Color(0xFF2b2149)], // Gradient colors  
          begin: Alignment.topLeft,  
          end: Alignment.bottomRight,  
        ),  
      ),  
      child: Scaffold(  
        backgroundColor: Colors.transparent,  
        // Make Scaffold background transparent to show the gradient  
        appBar: AppBar(  
  
          title:  const Text('Create Account',  
              style: TextStyle(  
                color: Colors.white,  
  
              )),  
          backgroundColor: Colors.transparent, // Make AppBar transparent  
          elevation: 0, // Remove shadow  
  
        ),  
        body: Padding(  
          padding: const EdgeInsets.all(16.0),  
          child: Form(  
            key: _formKey,  
            child: Column(  
              children: <Widget>[  
                Container(  
                  alignment: Alignment.centerLeft, // Aligns the text to the left  
                  child: Text(  
                    "Start your 30 day trial",  
                    style: TextStyle(color: Colors.blueGrey),  
                  ),  
                ),  
  
                SizedBox(height: 25,),  
                TextFormField(  
                  decoration: const InputDecoration(  
                    labelText: 'Email',  
                    prefixIcon: Icon(Icons.alternate_email_rounded),  
              filled: false,  
              fillColor: Colors.transparent,  
              contentPadding: EdgeInsets.symmetric(vertical: 10.0, horizontal: 16.0),  
              enabledBorder: OutlineInputBorder(  
                borderSide:  BorderSide(color: Colors.grey),)  
                  ),  
                  validator: (value) {  
                    if (value == null || value.isEmpty) {  
                      return 'Please enter your email';  
                    }  
                    final emailRegex = RegExp(r'^[^@]+@[^@]+\.[^@]+');  
                    if (!emailRegex.hasMatch(value)) {  
                      return 'Please enter a valid email';  
                    }  
                    return null;  
                  },  
                ),  
                //SizedBox.fromSize(size: const Size(0, 25,),  
                SizedBox(height: 25,),  
                TextFormField(  
                  controller: _passwordController,  
                  decoration: const InputDecoration(  
                      labelText: 'Name',  
                      prefixIcon: Icon(Icons.person),  
  
                      filled: false,  
                      fillColor: Colors.transparent,  
                      contentPadding: EdgeInsets.symmetric(vertical: 10.0, horizontal: 16.0),  
                      enabledBorder: OutlineInputBorder(  
                       borderSide:  BorderSide(color: Colors.grey),  
  
                      )),  
  
                  obscureText: true,  
  
                ),  
                SizedBox(height: 25,),  
                TextFormField(  
                  controller: _confirmPasswordController,  
                  decoration: const InputDecoration(  
                    labelText: 'Password',  
                      prefixIcon: Icon(Icons.lock),  
  
                      filled: false,  
                    fillColor: Colors.transparent,  
                    contentPadding: EdgeInsets.symmetric(vertical: 10.0, horizontal: 16.0),  
                    enabledBorder: OutlineInputBorder(  
                      borderSide:  BorderSide(color: Colors.grey),  
                  )  
                  ),  
                  obscureText: true,  
                  validator: (value) {  
                    if (value == null || value.isEmpty) {  
                      return 'Please enter your password';  
                    }  
                    if (value.length <8) {  
                      return 'Your password must be longer than 8';  
                    }  
                    return null;  
                  },  
                ),  
                const SizedBox(height: 10),  
                Container(  
                  alignment: Alignment.centerLeft, // Aligns the text to the left  
                  child: Text(  
                    "password must be 8 charactres least",  
                    style: TextStyle(color: Colors.blueGrey),  
                  ),  
                ),  
  
                const SizedBox(height: 20),  
                ElevatedButton(  
                  onPressed: () {  
                    if (_formKey.currentState!.validate()) {  
                      ScaffoldMessenger.of(context).showSnackBar(  
                        const SnackBar(content: Text('Processing Data')),  
                      );  
                    }  
                  },  
                  child: const Text('Create Account'),  
                ),  
                SizedBox(height: 25,),  
  
              ],  
            ),  
          ),  
        ),  
      ),  
    );  
  }  
}
```

result 

![](https://i.imgur.com/658gNkC.png)

