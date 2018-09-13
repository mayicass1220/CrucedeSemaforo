# CrucedeSemaforo
Programa para la creación de cruce de semáforos con Arduino Uno.
/*
  Código para un par de semaforos que cambian de uno
  a otro, y la implementacin de un boton para terminar
  el tiempo de la luz verde y pasar al otro.
*/

// Variable para el pin del boton
const int button = 8;

void setup() {
// Por medio de un ciclo se activan los pines del 2 al 7 como salidas
  for (int pin = 2; pin <= 7; pin++) {
    pinMode(pin, OUTPUT);
  }
  // El pin del boton se establece  como entrada
  pinMode(button, INPUT);
}
// A partir de estás lineas de código comienza la función para el primer semáforo y sus cambios de estado.
void semaphoreOne() {
  digitalWrite(2, HIGH);
  int count = 0;
  while (true) {
    if (digitalRead(button) == true) {
      break;
    }
  }
  digitalWrite(2, LOW);
  delay(500);
  digitalWrite(2, HIGH);
  delay(500);
  digitalWrite(2, LOW);
  delay(500);
  digitalWrite(2, HIGH);
  delay(500);
  digitalWrite(2, LOW);
  delay(500);
  digitalWrite(2, HIGH);
  delay(500);
  digitalWrite(2, LOW);
  delay(500);
  digitalWrite(2, HIGH);
  delay(500);
  digitalWrite(2, LOW);
  digitalWrite(3, HIGH);
  delay(2500);
  digitalWrite(3, LOW);
  digitalWrite(4, HIGH);
  digitalWrite(7, LOW);
  // Mandamos a llamar al segundo semáforo
  semaphoreTwo();
}
// Función para el segundo semáforo y sus cambios de estado
void semaphoreTwo() {
  digitalWrite(5, HIGH);
  int count = 0;
  while (true) {
    if (digitalRead(button) == true) {
      break;
    }
  }
  digitalWrite(5, LOW);
  delay(500);
  digitalWrite(5, HIGH);
  delay(500);
  digitalWrite(5, LOW);
  delay(500);
  digitalWrite(5, HIGH);
  delay(500);
  digitalWrite(5, LOW);
  delay(500);
  digitalWrite(5, HIGH);
  delay(500);
  digitalWrite(5, LOW);
  delay(500);
  digitalWrite(5, HIGH);
  delay(500);
  digitalWrite(5, LOW);
  digitalWrite(6, HIGH);
  delay(2500);
  digitalWrite(6, LOW);
  digitalWrite(7, HIGH);
  digitalWrite(4, LOW);
  // Mandamos a llamar al otro semáforo
  semaphoreOne();
}
// Inicia  semáforo
void loop() {
// Cambiamos el estado de todos los leds para
// que esten apagados todos al inicio
  for (int pin = 2; pin <= 7; pin++) {
    digitalWrite(pin, LOW);
	}
// Prendemos el verde de un semaforo y el
// rojo del otro semaforo
  digitalWrite(2, HIGH);
  digitalWrite(7, HIGH);
 // Iniciamos el primer semaforo
  semaphoreOne();
}
