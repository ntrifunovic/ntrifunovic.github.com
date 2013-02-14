title: I\O

#Input\Output
---

##C vs C++ I\O

U ovom kursu koristicemo C I\O (biblioteku stdio.h) za input i output

* zato sto je znatno brza u odnosu na C++ I\O (biblioteka iostream - cin i cout)
* metode koje cemo najvise koristiti su
	* `scanf`, `fscanf`, `sscanf`
	* `printf`, `fprintf`
	* `getchar`, `fgetc`
	* `gets`, `fgets`
	* `puts`, `fputs`
	* `putchar`, `fputc`
	* `fopen`
	
##Struktura C++ programa

Program koji ispisuje `Zdravo svete !!!`

	// Ovo je komentar
	/* I ovo je komentar */

	#include <stdio.h> // Koristimo standardnu biblioteku stdio

	int main() { // Ulazna tacka u program
		printf("Zdravo svete !!!"); // poziv metode za ispis na ekran iz biblioteke stdio
	
		return 0; // Vracamo vrednost 0, sto znaci da se nas program uspesno zavrsio
	} // Kraj metode main
		
Program koji sabira dva broja uneta sa tastature  
	
	// Program koji sabira dva broja uneta sa tastature
	
	#include <stdio.h> // Koristimo standardnu biblioteku stdio
	
	int main() { // Ulazna tacka u program
		int a, b; // Deklaracija promenjivih a i b tipa int
	
		// poziv metode scanf za citanje sa tastature iz biblioteke stdio
		scanf("%d%d", &a, &b); 
	
		printf("%d", a + b); // poziv metode za ispis na ekran iz biblioteke stdio
	
		return 0; // Vracamo vrednost 0, sto znaci da se nas program uspesno zavrsio
	} // Kraj metode main
	
## stdio.h

	FILE* fopen(const char* fileName, const char* mode);
	
`mode` moze biti

* `"r"` ako zelimo da citamo iz fajla
* `"w"` ako zelimo da pisemo u fajl

Povratna vrednost je pokazivac na objekat tipa `FILE` koji koristimo za pristup otvorenom fajlu.

Ako je doslo do greske prilikom otvaranja fajla povratna vrednost je `null` (pokazivac na nista).

---

	int getchar(); // cita sa standardnog ulaza
	int fgetc(FILE* f); // cita iz fajla
	
* Cita jedan karakter sa standardnog ulaza\fajla
* Povratna vrednost je procitani znak (njegov ASCII kod ili `EOF` ako se stiglo do kraja fajla)
	* `EOF` je konstanta koja se nalazi u stdio.h

---

	int putchar(int ch); 
	int fputc(int ch, FILE* f);
	
* Pise jedan karakter na standardni ulaz\fajl
* Vraca `ch` ako je upis uspeo, `EOF` ako je doslo do greske

---

	int scanf(const char* format, ...);
	int fscanf(FILE* f, const char* format, ...);
	
* Povratna vrednost je broj procitanih elemenata, `EOF` ako je doslo do greske
* `format` - Format ulaza koji se cita
* Posle formata sledi lista adresa promenjivih u koje se pamte ucitane vrednosti

---

	int printf(const char* format, ...);
	int fprintf(FILE* f, const char* format, ...);

* Povratna vrednost je broj ispisanih karaktera, negativna vrednost ako je doslo do greske
* `format` - Format izlaza koji se ispisuje
* Posle formata sledi lista promenjivih koje se ispisuju

---

###`scanf`, `printf`, `sscanf`, ...  parametar `format`

* `%c` 		`char`
* `%d` 		`long`, `int`
* `%u` 		`unsigned int`
* `%lld` 	`long long`
* `%f` 		`float`
* `%lf` 	`double`
* `%s` 		`char*`

* Opciono posle `%` moze ici `*` sto ce za posledicu imati da se procitani podatak ne pamti u neku promenjivu
* Postoje i drugi opcioni parametri vezani za formatiranje ulaza

