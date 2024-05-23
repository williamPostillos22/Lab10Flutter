import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: HomePage(),
    );
  }
}

class HomePage extends StatelessWidget {
  final List<Event> events = [
    Event(
      image: "https://concepto.de/wp-content/uploads/2015/02/futbol-1-e1550783405750.jpg",
      name: "Usuario 1",
      sport: "Fútbol",
      date: "10/05/2024",
      location: "Estadio Nacional",
    ),
    Event(
      image: "https://concepto.de/wp-content/uploads/2019/12/basquetbol-baloncesto-e1575657099957-800x399.jpg",
      name: "Usuario 2",
      sport: "Baloncesto",
      date: "12/06/2024",
      location: "Coliseo Cubierto",
    ),
    Event(
      image: "https://niberma.es/wp-content/uploads/2022/06/beneficios-de-jugar-tenis-actualizado.jpg",
      name: "Usuario 3",
      sport: "Tenis",
      date: "18/07/2024",
      location: "Campo Central",
    ),
    Event(
      image: "https://upload.wikimedia.org/wikipedia/commons/8/8c/Europei_di_pallavolo_2005_-_Italia-Russia.jpg",
      name: "Usuario 4",
      sport: "Voleibol",
      date: "24/08/2024",
      location: "Polideportivo",
    ),
    Event(
      image: "https://www.aquarakids.com/wp-content/uploads/2020/01/la-natacion-es-buena-1.jpg",
      name: "Usuario 5",
      sport: "Natación",
      date: "30/09/2024",
      location: "Piscina Olímpica",
    ),
  ];

  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Eventos Deportivos'),
      ),
      body: ListView.builder(
        itemCount: events.length,
        itemBuilder: (context, index) {
          return Card(
            child: Container(
              height: 200,
              child: Row(
                children: <Widget>[
                  Image.network(
                    events[index].image,
                    fit: BoxFit.cover,
                    width: 200, // Ancho fijo de 60 px
                    height: 280, // Altura fija de 40 px
                  ),
                  Expanded(
                    child: Padding(
                      padding: const EdgeInsets.only(left: 50.0),
                      child: Column(
                        mainAxisAlignment: MainAxisAlignment.end,
                        crossAxisAlignment: CrossAxisAlignment.start,
                        children: <Widget>[
                          Text(events[index].name, style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold)),
                          SizedBox(height: 10),
                          Text(events[index].sport),
                          SizedBox(height: 5),
                          Text(events[index].date),
                          SizedBox(height: 5),
                          Text(events[index].location),
                        ],
                      ),
                    ),
                  ),
                ],
              ),
            ),
          );
        },
      ),
    );
  }
}

class Event {
  final String image;
  final String name;
  final String sport;
  final String date;
  final String location;

  Event({
    required this.image,
    required this.name,
    required this.sport,
    required this.date,
    required this.location,
  });
}
