import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});


  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: 'BMI Calculator',
      theme: ThemeData(


       primarySwatch: Colors.indigo,
      ),
      home: const MyHomePage(),
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({Key? key}): super(key:key);

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {

  var wtContoller=TextEditingController();
  var cmContoller=TextEditingController();
  var result="";
  var bgColor=Colors.indigo.shade200;

  @override
  Widget build(BuildContext context) {
    return Scaffold(

        appBar: AppBar(

            title: Text("Your BMI")
        ),

        body: Center(

          child: Container(
            color: bgColor,
            width: 3000,
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [

                Text("BMI",style: TextStyle(
                  fontSize: 34, fontWeight: FontWeight.w700
                ),),

                SizedBox(height: 21,),

                TextField(
                  controller: wtContoller,
                  decoration: InputDecoration(
                    label: Text("Enter your weight(in Kg): "),
                    prefixIcon: Icon(Icons.line_weight)
                  ),
                  keyboardType: TextInputType.number,
                ),

                SizedBox(height: 11,),

                TextField(
                  controller: cmContoller,
                  decoration: InputDecoration(
                      label: Text("Enter your Height(in cm): "),
                      prefixIcon: Icon(Icons.height)
                  ),
                  keyboardType: TextInputType.number,
                ),

                SizedBox(height: 16,),

                ElevatedButton(onPressed: (){

                  var wt=wtContoller.text.toString();
                  var cm=cmContoller.text.toString();
                  if(wt!="" && cm!=""){

                    var iWt=int.parse(wt);
                    var iCM=int.parse(cm);
                    var tM=iCM/100;
                    var bmi=iWt/(tM*tM);
                    var msg="";

                    if(bmi>25){
                      msg="You are Overweight";
                      bgColor=Colors.orange.shade200;
                    }else if(bmi<18){
                      msg="You are Underweight!!";
                      bgColor=Colors.red.shade200;
                    }else{
                      msg="You are Healthy!!";
                      bgColor=Colors.green.shade200;

                    }

                    setState(() {
                      result="$msg \n Your BMI is: ${bmi.toStringAsFixed(2)}";
                    });


                  }else{
                    setState(() {
                      result="Please fill all the required blanks!!";
                    });
                  }

                }, child: Text("Calculate")),

                SizedBox(height: 11,),
                
                Text(result,style: TextStyle(fontSize: 19),)
              ],
            ),
          ),
        )
    );
  }
}
