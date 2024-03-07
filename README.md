import 'package:flutter/material.dart';
import 'dart:math';
void main() {
  runApp(const MyApp());
  runApp(WhatsAppMessage());
}



class WhatsAppMessage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('WhatsApp Message'),
        ),
        body: Center(
          child: UnreadMessage(),
        ),
      ),
    );
  }
}

class UnreadMessage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Container(
      padding: EdgeInsets.all(20.0),
      decoration: BoxDecoration(
        color: Colors.green, // Couleur du message non lu
        borderRadius: BorderRadius.circular(10.0),
      ),
      child: Row(
        mainAxisAlignment: MainAxisAlignment.spaceBetween,
        children: [
          Icon(
            Icons.message,
            color: Colors.white,
          ),
          SizedBox(width: 10.0),
          Expanded(
            child: Text(
              '3 nouveaux messages', // Contenu du message non lu
              style: TextStyle(
                color: Colors.white,
                fontSize: 16.0,
              ),
            ),
          ),
          SizedBox(width: 10.0),
          Icon(
            Icons.arrow_forward,
            color: Colors.white,
          ),
        ],
      ),
    );
  }
}


class MyApp extends StatelessWidget {
  const MyApp({super.key});


  @override
  Widget build(BuildContext context) {

    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: "Application",
      home: PageHome(),

    );
  }
}
class Person{
  String? name, sexe;
  int? age, size, message;
  Person({
    this.age,
    this.size,
    this.nom,
    this.sexe,
    this.message,
});
}

class PageHome extends StatelessWidget {
  const PageHome({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Center(child: Text("ChatApp"),),
        backgroundColor: Color(0xFF2ac0ac),
      ),
      body: BodySection(),
      floatingActionButton: FloatingActionButton(
        backgroundColor: Color(0xFF2ac0ac),
        child: Icon(Icons.add),
        onPressed: (){},
      ),
      bottomNavigationBar: NavigationBar(
        selectedIndex: 1,
        destinations: const <Widget>[
          NavigationDestination(icon: Icon(Icons.wifi, color: Color(0xFF2ac0ac)), label: "Statut", ),
          NavigationDestination(icon: Icon(Icons.message, color: Color(0xFF2ac0ac),), label: "Messagerie"),
          NavigationDestination(icon: Icon(Icons.call, color: Color(0xFF2ac0ac),), label: "call"),
        ],
      ),
    );
  }
}

class BodySection extends StatelessWidget {
  const BodySection({super.key});

  @override
  Widget build(BuildContext context) {
    Person person1 = new Person(name: "junior AGBODJOGBE",sexe: 'M', age: 22, size: 110, message: 200);
    Person person2 = new Person(name: "Samiel ZANNOU",sexe: 'F', age: 45, size: 120, message: 4);
    Person person3 = new Person(name: "Joas OKE",sexe: 'M', age: 40, size: 130, message: 24);
    Person person4 = new Person(name: "KAKA MILAN",sexe: 'F', age: 90, size: 140, message: 1);




    var personne = [person1, person2, person3, person4
    ];
    return Container(

      padding: EdgeInsets.only(right: 10, left: 10, top: 5, bottom: 6),
      child: ListView(
        //scrollDirection: Axis.vertical,
        children: [
          /*InkWell(
            onTap: (){},
            splashColor: Color(0xff79b9b1),
            child: ListTile(
              leading: CircleAvatar(),
              title: Text("ddd"),
              subtitle: Text("jjddj"),
            ),

          ),
          InkWell(
            onTap: (){},
            splashColor: Color(0xff79b9b1),
            child: ListTile(
              leading: CircleAvatar(),
              title: Text("ddd"),
              subtitle: Text("jjj"),
            ),

          ),
          */

          ...personne.map((e) =>
            InkWell(
              onTap: (){print('object');},
              splashColor: Color(0xff79b9b1),
              child: ListTile(
                leading: CircleAvatar(backgroundImage: AssetImage('images/pilier.jpg'),),

                title: Text(e.name.toString()),
                subtitle: Text("moi je m'appelle"+ e.name.toString() +" \n\t\rVoici mes info : taille :" + e.size.toString() + "cm"+ " age:"+e.age.toString()),
                trailing: Container(
                  padding: EdgeInsets.all(7),
                  decoration: BoxDecoration(
                    color: Color(0xFF2ac0ac),
                    shape: BoxShape.circle,
                  ),
                  child: Text(
                    e.message.toString(),
                    style: TextStyle(
                      color: Colors.white,
                    ),
                  ),
                ),
              ),
            )
          ).toList(),
        ],
      ),
    );

  }
}




import 'package:flutter/material.dart';
import 'dart:math';
void main() {
  runApp(const MyApp());
  runApp(WhatsAppMessage());
}



class WhatsAppMessage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('WhatsApp Message'),
        ),
        body: Center(
          child: UnreadMessage(),
        ),
      ),
    );
  }
}

class UnreadMessage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Container(
      padding: EdgeInsets.all(20.0),
      decoration: BoxDecoration(
        color: Colors.green, // Couleur du message non lu
        borderRadius: BorderRadius.circular(10.0),
      ),
      child: Row(
        mainAxisAlignment: MainAxisAlignment.spaceBetween,
        children: [
          Icon(
            Icons.message,
            color: Colors.white,
          ),
          SizedBox(width: 10.0),
          Expanded(
            child: Text(
              '3 nouveaux messages', // Contenu du message non lu
              style: TextStyle(
                color: Colors.white,
                fontSize: 16.0,
              ),
            ),
          ),
          SizedBox(width: 10.0),
          Icon(
            Icons.arrow_forward,
            color: Colors.white,
          ),
        ],
      ),
    );
  }
}


class MyApp extends StatelessWidget {
  const MyApp({super.key});


  @override
  Widget build(BuildContext context) {

    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: "Application",
      home: PageHome(),

    );
  }
}
class Person{
  String? name, sexe;
  int? age, size, message;
  Person({
    this.age,
    this.size,
    this.nom,
    this.sexe,
    this.message,
});
}

class PageHome extends StatelessWidget {
  const PageHome({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Center(child: Text("ChatApp"),),
        backgroundColor: Color(0xFF2ac0ac),
      ),
      body: BodySection(),
      floatingActionButton: FloatingActionButton(
        backgroundColor: Color(0xFF2ac0ac),
        child: Icon(Icons.add),
        onPressed: (){},
      ),
      bottomNavigationBar: NavigationBar(
        selectedIndex: 1,
        destinations: const <Widget>[
          NavigationDestination(icon: Icon(Icons.wifi, color: Color(0xFF2ac0ac)), label: "Statut", ),
          NavigationDestination(icon: Icon(Icons.message, color: Color(0xFF2ac0ac),), label: "Messagerie"),
          NavigationDestination(icon: Icon(Icons.call, color: Color(0xFF2ac0ac),), label: "call"),
        ],
      ),
    );
  }
}

class BodySection extends StatelessWidget {
  const BodySection({super.key});

  @override
  Widget build(BuildContext context) {
    Person person1 = new Person(name: "junior AGBODJOGBE",sexe: 'M', age: 22, size: 110, message: 200);
    Person person2 = new Person(name: "Samiel ZANNOU",sexe: 'F', age: 45, size: 120, message: 4);
    Person person3 = new Person(name: "Joas OKE",sexe: 'M', age: 40, size: 130, message: 24);
    Person person4 = new Person(name: "KAKA MILAN",sexe: 'F', age: 90, size: 140, message: 1);




    var personne = [person1, person2, person3, person4
    ];
    return Container(

      padding: EdgeInsets.only(right: 10, left: 10, top: 5, bottom: 6),
      child: ListView(
        //scrollDirection: Axis.vertical,
        children: [
          /*InkWell(
            onTap: (){},
            splashColor: Color(0xff79b9b1),
            child: ListTile(
              leading: CircleAvatar(),
              title: Text("ddd"),
              subtitle: Text("jjddj"),
            ),

          ),
          InkWell(
            onTap: (){},
            splashColor: Color(0xff79b9b1),
            child: ListTile(
              leading: CircleAvatar(),
              title: Text("ddd"),
              subtitle: Text("jjj"),
            ),

          ),
          */

          ...personne.map((e) =>
            InkWell(
              onTap: (){print('object');},
              splashColor: Color(0xff79b9b1),
              child: ListTile(
                leading: CircleAvatar(backgroundImage: AssetImage('images/pilier.jpg'),),

                title: Text(e.name.toString()),
                subtitle: Text("moi je m'appelle"+ e.name.toString() +" \n\t\rVoici mes info : taille :" + e.size.toString() + "cm"+ " age:"+e.age.toString()),
                trailing: Container(
                  padding: EdgeInsets.all(7),
                  decoration: BoxDecoration(
                    color: Color(0xFF2ac0ac),
                    shape: BoxShape.circle,
                  ),
                  child: Text(
                    e.message.toString(),
                    style: TextStyle(
                      color: Colors.white,
                    ),
                  ),
                ),
              ),
            )
          ).toList(),
        ],
      ),
    );

  }
}



