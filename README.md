# js_averageGrades
```bash

 
function test() {
    const students = [
        {
            name: "Jan",
            surname: "Kowalski",
            age: 21,
            index: "12345",
            grades: [4, 5, 3, 2],
        },
        {
            name: "Anna",
            surname: "Nowak",
            age: 22,
            index: "23456",
            grades: [5, 5, 5, 4],
        },
        {
            name: "Piotr",
            surname: "Wisniewski",
            age: 20,
            index: "34567",
            grades: [3, 3, 2, 2],
        },
    ];
 
    function calculateAverageGrade(students) {
        let averageGrades = {};
 
        for (let student of students) {
            let studentGrades = student.grades;
            let average =
                studentGrades.reduce((a, b) => a + b) / studentGrades.length;
            averageGrades[student.surname] = average;
        }
 
        let overallAverage =
            Object.values(averageGrades).reduce((a, b) => a + b) /
            students.length;
 
        console.log(
            `Średnia ocen dla każdego studenta (${Object.keys(
                averageGrades
            )}): ${averageGrades["Kowalski"]}, ${averageGrades["Nowak"]}, ${
                averageGrades["Wisniewski"]
            }`
        );
        console.log(`Ogólna średnia ocen: ${overallAverage.toFixed(2)}`);
    }
 
    calculateAverageGrade(students);
}
 
test();
```
## alert, prompt
```bash

function greetUser() {
  const name = prompt("Jak masz na imie?");


if (name) {
    alert(`Witaj ${name}! Milo Cie poznac.`);
} else {
    alert("Nie podales swojego imienia. Sprobuj jeszcze raz.");
}
}

//  <button onclick="greetUser()">Kliknij, aby się przywitać</button>   =>HTML
```
# confirm => zapytanie o pewność decyzji
```bash
function askConfirmation() {
  const decisionConfirmed = confirm("Czy na pewno chcesz wykonać zakończyć?");
  
    if (decisionConfirmed) {
        alert("Twoja decyzja została potwierdzona.");
    } else {
        alert("Twoja decyzja została anulowana.");
    }
}
//  <button onclick="askConfirmation()">Kliknij, aby zadać pytanie</button> => HTML
```
# Bolean i Number
```bash function test() {
    let koszt = "25.50";
    
    let kosztLiczba =  Number(koszt);
    let kosztAkcept = Boolean (kosztLiczba > 20);
    
    if (kosztAkcept) {
        console.log("Zamowienie zaakceptowane");
    } else {
        console.log("Koszt zamowienia musi byc wiekszy niz 20 zl");
    }
}
    


test();
```
## 
Inkrementacja / Dekrementacja => zwiększ/zmniejsz licznik

```bash
let licznik = 0;
function zwiekszLicznik() {
    licznik ++
    aktualizujWynik();
}
function zmniejszLicznik() {
  licznik--;
  aktualizujWynik();
}
function aktualizujWynik() {
  document.getElementById("wynik").textContent = licznik;
}

aktualizujWynik();

//    <button onclick="zwiekszLicznik()">Zwiększ licznik</button>
// <button onclick="zmniejszLicznik()">Zmniejsz licznik</button>
// <div id="wynik">0</div>
```
# sprawdzenie czy uzytkownik spełnia warunki by prowadzić pojazd
```bash


function test() {
    const minAge = 18;
    
    const age = parseInt(prompt("Podaj swoj wiek:"));
    const hasLicense = prompt("Czy posiadasz prawo jazdy? (Tak/Nie)");
    
    if (age >= minAge && hasLicense.toLowerCase() === "tak") {
        alert("Mozesz wypozyczyc samochod!");
    } else {
        alert("Nie mozesz wypozyczyc samochodu. Brak wymaganych dokumentow / niepelnoletni.")
    }
    

}

test();
```
# porównanie
```bash


function test() {
    let name = null;
    let surname;
    
    console.log(name == surname);
    console.log(name === surname);
}
    
    
test();
```
# podatek Vat
```bash


function test() {
    let basePrice = 50;
    let vatRate = 0.23;
    
    let vatAmount = basePrice * vatRate;
    
    let totalPrice = basePrice + vatAmount;
    
    console.log("Bazowa cena:", basePrice);

    console.log("Podatek VAT:", vatAmount);

    console.log("Całkowita cena:", totalPrice);
    
     
}

test();
```
## Math.floor(), Math.ceil(), Math.round() 
```bash
function test() {
    let number = 3.7;
    let floorResult = Math.floor(number); // do najbliższej liczby całkowitej w DÓŁ
    let ceilResult = Math.ceil(number);  //  do najbliższej liczby całkowitej w GÓRĘ
    let roundResult = Math.round(number); // do najbliższej liczby całkowitej
}
test()
```
## isNaN / isFinite
```bash
function test() {
    function validateNumber(number) {
        if (isNaN(number)) {
            console.log("Podana wartosc nie jest liczba.");
        } else if (!isFinite(number)) {
            console.log("Podana liczba jest nieskonczona.");
        } else {
            console.log("Podana wartosc jest prawidlowa liczba.");
        }
    }
 
    validateNumber(10); // Prawidlowa liczba
    validateNumber("ABC"); // Nie jest liczba
    validateNumber(Infinity); // Nieskonczonosc
}
 
test();
```
# OPERACJE NA STRINGACH  
##  str - wyświetlenie długości zdania, pierwszej i ostatniej litery, sprawdzenie, czy zdanie zawiera określone słowo..- .includes !!!
```bash



function test() {
     const sentence = "To jest przykladowe zdanie.";
     console.log(`Dlugosc zdania: ${sentence.length}`);
     console.log(`Pierwsza litera zdania: ${sentence[0]}`);
     console.log(`Ostatnia litera zdania: ${sentence[sentence.length - 1]}`);
     
     const wordToCheck = "przykladowe";
     // .includes !!!
    console.log(`Czy zdanie zawiera slowo "${wordToCheck}"? ${sentence.includes(wordToCheck)}`);

    // zmiana pierwszej litery zdania na małą 
    
    const modifiedSentence = sentence[0].toLowerCase() + sentence.slice(1);
    console.log(`Zmodyfikowane zdanie: ${modifiedSentence}`);
    // .slice => WYCINAMY FRGM TEKSTU OD DANEGO MIEJSCA

}

test();
```
## String - metody slice / substring / substr
```bash


function test() {
     const sentence = "To jest przykladowe zdanie."
     console.log(sentence);
     let fragment1 = sentence.slice(2,10); // frgm zdania od 3 do 11
     console.log(fragment1);
     let fragment2 = sentence.substring(11,18); // frgm zdania od 12 do 19 
     console.log(fragment2);
     let fragment3 = sentence.substr(20,6); //  fragment zdania zaczynający się od 21 znaku i mający długość 6 znaków  
     console.log(fragment2);
     
}

test();
```
# test czy masz wystarczający wzrost
```bash
function test() {
    // Miejsce na kod JS
    const MINIMALNY_WZROST = 150;
 
    let wzrost = prompt("Podaj swoj wzrost w centymetrach:");
 
    if (isNaN(wzrost)) {
        alert("Podaj poprawna wartosc liczbowa!");
    } else {
        if (wzrost >= MINIMALNY_WZROST) {
            alert("Mozesz skorzystac z karuzeli!");
        } else {
            alert("Jestes za niski, zeby skorzystac z karuzeli.");
        }
    }
}
 
test();
// <button onclick="test()">Kalkulator wzrostu</button> => HTML
```
# if-else BOOLEAN
```bash
function test() {
    // Miejsce na kod JS
    const czyChceszPizze = true;
 
    if (czyChceszPizze) {
        console.log("Super, jedziemy po pizze!");
    } else {
        console.log("Okej, może nastepnym razem.");
    }
}
 
test();
```
# warunek ? wartość_jeśli_prawda : wartość_jeśli_fałsz - operator warunkowy trójargumentowy ?
```bash
function test() {
 
    let age = 14;
 
    let status = age >= 18 ? true : false;
 
    if (status) {
        console.log("Jestes pelnoletni!");
    } else {
        console.log("Nie jestes jeszcze pelnoletni.");
    }
}
 
test();
```
# .prompt(), parseInt(), operatory logiczne
```bash
function test() {
   let year = parseInt(prompt("Wpisz rok "));
   let isLeapYear = (year % 4 === 0 && year % 100 !== 0) || year % 400 === 0;
   if (year >= 2001 && year <= 2100 && isLeapYear) {
       alert(`${year} jest przestepny i nalezy do XXI wieku.`);
    } else if (year >= 2001 && year <= 2100 && !isLeapYear) {
        alert(`${year} nie jest przestepny i nalezy do XXI wieku.`);
    } else {
        alert(`${year} nie nalezy do XXI wieku.`);
   }
   

}

test();
```
## Operator koalescencji 
```bash
function test() {
    
    let price = 3200;
    let isRegularCustomer = true;
    let numberOfPurchases = 3;
    let discount = isRegularCustomer
        ? (numberOfPurchases ?? 0) >= 3
            ? 10
            : 0
        : 0;
    let totalPrice = price - (price * discount) / 100;
 
    console.log(`Cena roweru: ${totalPrice} pln`);
}
 
test();
```
# kalkulator kalorii , while 
```bash
function test() {
    
 
    let sumaKalorii = 0;
    let wprowadzoneKalorie;
 
    while (wprowadzoneKalorie !== "stop") {
        wprowadzoneKalorie = prompt(
            "Podaj kalorycznosc kolejnego posilku (lub wpisz 'stop' by zakonczyc):"
        );
        if (wprowadzoneKalorie !== "stop") {
            sumaKalorii += parseInt(wprowadzoneKalorie);
        }
    }
 
    alert(`laczna liczba spozytych kalorii: ${sumaKalorii}`);
}
 
test();
```
# zgadnij liczbę ,while
```bash

            const szukanaLiczba = Math.floor(Math.random() * 10) + 1;
             
            alert("Witaj w loterii! Zgadnij liczbe od 1 do 10. Masz 5 prob.");
             
            let liczbaProb = 5;
             
            while (liczbaProb > 0) {
                const zgadywanaLiczba = parseInt(prompt("Podaj liczbe:"));
             
                if (zgadywanaLiczba == szukanaLiczba) {
                    alert("Gratulacje! Zgadles(as)!");
                    break;
                } else if (zgadywanaLiczba < szukanaLiczba) {
                    alert("Podana liczba jest za mala. Sprobuj ponownie.");
                } else {
                    alert("Podana liczba jest za duza. Sprobuj ponownie.");
                }
             
                liczbaProb--;
            }
             
            if (liczbaProb === 0) {
                alert("Przegrales(as)! Szukana liczba to: " + szukanaLiczba);
            }
```
# kalkulator cen - do while;
```bash

function test() {
    let suma = 0;
    let cena;
    do {
         cena = parseFloat(prompt("Podaj cene: (wpisz 0, by zakończyć"));
        suma += cena;
    } while (cena !== 0);
    alert("Łączna wartość produktów wynosi:" + suma.toFixed(2));
    
    
    
}


test();
```
# pepier kamień nożyce
```bash
 const opcje = ["kamien", "papier", "nozyce"];
 
    alert(
        'Witaj w grze Kamien, Papier, Nozyce! Rozpocznij gre lub wpisz "q", aby zakonczyc.'
    );
 
    do {
        const wyborUzytkownika = prompt(
            'Wybierz: kamien, papier, nozyce (lub "q" aby zakonczyc):'
        );
 
        if (wyborUzytkownika === "q") {
            alert("Dziekujemy za gre. Do widzenia!");
            break;
        }
 
        const losowyIndeks = Math.floor(Math.random() * opcje.length);
        const wyborKomputera = opcje[losowyIndeks];
 
        if (wyborUzytkownika === wyborKomputera) {
            alert("Remis! Wybraliscie obie strony " + wyborUzytkownika + ".");
        } else if (
            (wyborUzytkownika === "kamien" && wyborKomputera === "nozyce") ||
            (wyborUzytkownika === "papier" && wyborKomputera === "kamien") ||
            (wyborUzytkownika === "nozyce" && wyborKomputera === "papier")
        ) {
            alert(
                "Gratulacje! Wygrales! Twoj " +
                    wyborUzytkownika +
                    " pokonuje " +
                    wyborKomputera +
                    "."
            );
        } else {
            alert(
                "Przegrales! Twoj " +
                    wyborUzytkownika +
                    " jest pokonany przez " +
                    wyborKomputera +
                    "."
            );
        }
    } while (true);
```
# zlczenie ile liter ma kazde słowo w zdaniu - pętla for 
```bash
function policzDlugoscSlowa(zdanie) {
    const slowa = zdanie.split(" ");
    const dlugosci = [];
 
    for (let i = 0; i < slowa.length; i++) {
        const dlugosc = slowa[i].length;
        dlugosci.push(dlugosc);
    }
 
    return dlugosci;
}
 
const zdanie = "To jest przykladowe zdanie do analizy";
const dlugosciSlow = policzDlugoscSlowa(zdanie);
 
console.log("Dlugosci slow w zdaniu:", dlugosciSlow);
```
# wyliczenie średniej temperatury , pętla for
```bash
function test() {
    
    const temperatures = [25, 30, 28, 22, 27];
    let sum = 0;
 
    for (let i = 0; i < temperatures.length; i++) {
        sum += temperatures[i];
    }
 
    const average = sum / temperatures.length;
    console.log("Srednia temperatura wynosi: " + average);
}
 
test();
```
# znajdz perwszą liczę pierwszą w tablicy liczb 
```bash
function test() {
    // Miejsce na kod JS
    const numbers = [10, 7, 4, 12, 11, 20, 9, 13];
 
    function isPrime(number) {
        if (number < 2) {
            return false;
        }
 
        for (let i = 2; i < number; i++) {
            if (number % i === 0) {
                return false;
            }
        }
 
        return true;
    }
 
    for (let i = 0; i < numbers.length; i++) {
        if (isPrime(numbers[i])) {
            console.log("Pierwsza liczba znaleziona: " + numbers[i]);
            break;
        }
    }
}
 
test();
```
# obliczenie średniej ocen 
```bash
function test() {
    // Miejsce na kod JS
    const grades = [3, 4, 5, 2, 3, 5, 4, 2, 4, 5];
    let sum = 0;
    let count = 0;
 
    for (let i = 0; i < grades.length; i++) {
        if (grades[i] < 3) {
            continue;
        }
 
        sum += grades[i];
        count++;
    }
 
    const average = sum / count;
    console.log(
        "Srednia ocen (bez ocen niedostatecznych): " + average.toFixed(2)
    );
}
 
test();
```
# obliczenie kosztu wysyłki w żależności od formy dostawy - switch
```bash
function test() {
    // Miejsce na kod JS
    const deliveryMethod = "kurier";
    let cost = 0;
 
    switch (deliveryMethod) {
        case "kurier":
            cost = 15;
            break;
        case "poczta":
            cost = 10;
            break;
        case "odbior osobisty":
            cost = 0;
            break;
        default:
            console.log("Nieznana metoda dostawy.");
    }
 
    console.log("Koszt wysylki: " + cost + " pln");
}
 
test();
```
# greeting in different languages
```bash
const languageCode = "en";
        function greet() {
          switch (languageCode) {
            case "en":
              console.log("Hello!");
              break;
            case "es":
              console.log("¡Hola!");
              break;
            case "fr":
              console.log("Bonjour !");
              break;
            default:
              console.log("Unsupported language.");
          }
        }
        
    
greet();
```
# kalkulate BMI 
```bash
 
    function test() {
        function calculateBMI(height, weight) {
            const heightInMeters = height / 100; // Konwersja wzrostu z cm na metry
            const bmi = weight / (heightInMeters * heightInMeters);
            return bmi;
        }
     
        const height = 180; // Wzrost w cm
        const weight = 75; // Waga w kg
     
        const bmiResult = calculateBMI(height, weight);
        console.log("Twoj wskaznik BMI wynosi: " + bmiResult.toFixed(2));
    }
     
    test();
```
# calculate Tax
```bash
function test() {
    function calculateTax(value, taxRate = 0.23) {
    const tax = value * taxRate;
    return tax;
    }
    
    console.log(calculateTax(100));
    console.log(calculateTax(100, 0.15));
}

test();
```
# oblicz średnia ocen

```bash



function test() {
    const oceny = [4, 3.5, 5, 4.5, 3, 4];
    const obliczSrednia = function(oceny) {
        let suma = 0;
        for(let i = 0; i< oceny.length; i++) {
        suma += oceny[i];
    }
    const srednia = suma / oceny.length;
    return srednia;
    
};
const wynik = obliczSrednia(oceny);
console.log(`Srednia wartosc ocen: ${wynik}`);

}

test();
```
# Funkcja zwrotna (callback) - przetwarzanie danych bez interakcji z użytkownikiem.
```bash


function test() {
    
    function calculateAverageTemperature(temperatureData, callback) {
        const sum = temperatureData.reduce(
            (total, temperature) => total + temperature,
            0
        );
        const average = sum / temperatureData.length;
        callback(average);
    }
 
    const temperatureData = [23, 24, 22, 25, 21];
 
    function displayAverageTemperature(average) {
        console.log(`Srednia temperatura: ${average}`);
    }
 
    calculateAverageTemperature(temperatureData, displayAverageTemperature);
}
 
test();
```
# obliczenie sumy liczb za pomocą funkcji strzałkowej
```bash
function test() {
   
    const calculateSum = (array) => {
        let sum = 0;
        array.forEach((number) => {
            sum += number;
        });
        return sum;
    };
 
    const numbers = [1, 2, 3, 4, 5];
    const result = calculateSum(numbers);
    console.log(result);
}
 
test();
```
# Funkcja strzałkowa z parametrami i wartościami domyślnymi
```bash
function test() {
    
    const calculateBankFee = (kwota, typTransakcji, oprocentowanie = 0.05) => {
        let oplata = 0;
 
        if (typTransakcji === "przelew") {
            oplata += 1.5;
        } else if (typTransakcji === "wplata") {
            oplata += 0.5;
        }
 
        oplata += kwota * oprocentowanie;
 
        return oplata;
    };
 
    // Przykladowe użycie funkcji
    let kwotaTransakcji = 1000;
    let typ = "przelew";
    let oplataBankowa = calculateBankFee(kwotaTransakcji, typ);
 
    console.log(`Oplata bankowa: ${oplataBankowa}`);
}
 
test();
```
# Funkcja strzałkowa z funkcją zwrotną - FILTROWANIE LISTY PRODUKTÓW NA PODSTAWIE OKREŚLONYCH KRYTERIÓW
```bash
function test() {
    // Miejsce na kod JS
    const products = [
        { name: "Koszula", price: 49.99 },
        { name: "Spodnie", price: 79.99 },
        { name: "Buty", price: 129.99 },
        { name: "Kurtka", price: 149.99 },
    ];
 
    const filterProducts = (filterFunction) => {
        const filteredProducts = products.filter(filterFunction);
        return filteredProducts;
    };
 
    const filteredProducts = filterProducts((product) => product.price < 100);
    console.log(filteredProducts[0].name + ": " + filteredProducts[0].price);
    console.log(filteredProducts[1].name + ": " + filteredProducts[1].price);
}
 
test();
```
# this & new
```bash
function test() {
    
 
    function Person() {
        const self = this;
 
        self.name = "";
 
        self.setName = function (name) {
            self.name = name;
        };
    }
 
    const person = new Person();
    person.setName("John");
    console.log(person.name);
}
 
test();
```
# prototype, funkcja konstruktora , zadania 
```bash


function test() {
    function Task(title, description) {
        this.title = title;
        this.description = description;
    }
    
    
    // definuje metodę raz i udostępnienia ją dla wszystkich instancji obiektu Task
    Task.prototype.printTask = function () {
        console.log(`Zadanie: ${this.title}`);
        console.log(`Opis: ${this.description}`);
    };
    const task1 = new Task("Zakupy spozywcze", "Kupic jajka, mleko i chleb");
}

task1.printTask();

test();

```
# inicjalizator obiektów, zarządzanie zamówieniami
```bash
function test() {
    const Order = (id, product, quantity) => ({
        id,
        product,
        quantity,
    });
    const order1 = Order(1, "Koszula", 2);
    console.log(`Id zamowienia: ${order1.id}`);
    console.log(`Produkt: ${order1.product}`);
    console.log(`Ilosc: ${order1.quantity}`);
}

test();
```
# Object.create()
```bash


function test() {
    const userPrototype = {
        introduce() {
        console.log(`Hi, my name is ${this.name}. I am ${this.age} years old.`);
        },
    };
    
    function createUser(name, age) {
        const user = Object.create(userPrototype);
        user.name = name;
        user.age = age;
        return user;
    }
    const user1 = createUser("John", 25);
    user1.introduce();
}

test();
```
# Dostęp do właściwości obiektu , modyfikowanie właściwości obiektu
```bash


function test() {
    const products = [
        { name: "Product 1", price: 10.99, quantity: 50 },
        { name: "Product 2", price: 5.99, quantity: 20 },
        { name: "Product 3", price: 15.99, quantity: 10 },
    ];
    
    products.forEach((product) => {
        console.log("Product name:", product.name);
        console.log("Price:", product.price);
        console.log("Quantity:", product.quantity);
    });
    
    const product2 = products.find((product) => product.name === "Product 2");
    console.log("Price of Product 2:", product2.price);
    
     const product3 = products.find((product) => product.name === "Product 3");
     product3.quantity += 5;
     console.log("New quantity of Product 3:", product3.quantity);
}

test();
```
# Klonowanie obiektów - Object.assign()
```bash


function test() {
    let person = {
        name: "John Doe",
        age: 30,
        address: {
            street: "Main Street",
            city: "City",
            country: "Country",
         },
    };
    
    const cloneObject = (source, target) => {
        Object.assign(target, source);
    };
    const clonedPerson = {};
    
    cloneObject(person, clonedPerson);
    
    person.name = "Jane Smith";
    person.age = 25;
    person.address.city = "New City"
    
    console.log("Original person:", person);
    console.log("Cloned person:", clonedPerson);
    
}

test();
```
# for...in - iterowanie po właściwościach obiektu
```bash


function test() {
    const bookCollection = {
        book1: {
            author: 'Autor 1',
            year: 2000,
        },
        book2: {
            author: 'Autor 2',
            year: 2005,
        },
        book3: {
            author: 'Autor 3',
            year: 2010,
        },
    };
    
    function iterateBookCollection(bookCollection) {
        for (const bookName in bookCollection) {
            const bookDetails = bookCollection[bookName];
            console.log(`Ksiazka: ${bookName}`);
            console.log(`Autor: ${bookDetails.author}`);
            console.log(`Rok wydania: ${bookDetails.year}`);
        }
    }
    
    iterateBookCollection(bookCollection);
}

test();
```
#  for...of iterowanie przez elementy tablicy 
#  aplikacaę do zarządzania listą zadań, gdzie będzie się iterować przez zadania i wykonywać różne operacje na nich.

```bash


function test() {
    const tasks = [
        { name: 'Zakupy spozywcze', completed: false },
        { name: 'Sprzatanie mieszkania', completed: true },
        { name: 'Nauka JavaScript', completed: false }
    ];
    
            function manageTasks(tasks) {
                for (const task of tasks) {
                    console.log(`Zadanie: ${task.name}`);
                    console.log(`Czy wykonane: ${task.completed ? 'Tak' : 'Nie'}`);
            
            }
            
           
          
        }
         manageTasks(tasks);
}

test();

```
#  Symulacja aplikacji do zarządzania playlistą muzyczną. Tworzenie obiektu playlisty, który będzie zawierał funkcje do dodawania utworów, wyświetlania listy utworów oraz odtwarzania aktualnego utworu.
```bash
function test() {
    
    const playlist = {
        currentSongIndex: 0,
        songs: [],
        addSong(name) {
            this.songs.push(name);
        },
        showPlaylist() {
            for (const song of this.songs) {
                console.log(song);
            }
        },
        playCurrentSong() {
            const currentSong = this.songs[this.currentSongIndex];
            console.log(`Odtwarzam: ${currentSong}`);
        },
    };
 
    playlist.addSong("NF - HOPE");
    playlist.addSong("Perfect - Autobiografia");
    playlist.addSong("Imagine Dragons - Wrecked");
 
    playlist.showPlaylist();
    playlist.playCurrentSong();
}
 
test();

















