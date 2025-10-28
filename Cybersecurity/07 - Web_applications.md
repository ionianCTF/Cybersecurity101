# Cyber Security **Web Applications**

## Εισαγωγή
Οι **Web εφαρμογές** είναι απαραίτητες για σχεδόν κάθε δραστηριότητα, είτε για πρόσβαση στο Internet, είτε για απομακρυσμένο έλεγχο συσκευών. Σε αυτό το εισαγωγικό μάθημα θα καλύψουμε τα βασικά της ασφάλειας web εφαρμογών.

## Το πρωτόκολλο HTTP
Το **HTTP** είναι το πρωτόκολλο που επιτρέπει στους browsers και τις εφαρμογές να λαμβάνουν περιεχόμενο όπως HTML, CSS, εικόνες και βίντεο.

## URLs, Παράμετροι Query και Scheme
Παράδειγμα URL:
````
https://www.google.com/search?q=w3schools+cyber+security&ie=UTF-8
````
Στοιχεία URL:
- Domain: google.com
- Script: /search
- Query Parameters: q, ie

Το `/` δείχνει την κορυφαία διαδρομή στον server. Το `?` ξεκινά τις παραμέτρους εισόδου. Το `&` διαχωρίζει διαφορετικές παραμέτρους.

Το **Scheme** καθορίζει το πρωτόκολλο (HTTP, HTTPS, FTP, SSH, SMB).

## HTTP Headers
Παράδειγμα HTTP request:
````http
GET /search?q=w3schools+cyber+security&ie=UTF-8 HTTP/1.1
Host: google.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) ...
Accept: image/avif,image/webp,image/apng,image/*,*/*;q=0.8
Referer: https://w3schools.com/
Accept-Encoding: gzip, deflate
Cookie: cookie1=value1;cookie2=value2
````

**Επεξήγηση Headers:**
| Header | Εξήγηση |
|--------|---------|
| GET /search... HTTP/1.1 | HTTP verb GET ζητά πρόσβαση στην εφαρμογή |
| Host: google.com | Στοχεύει την υπηρεσία του server |
| User-Agent | Αναγνωρίζει τον client |
| Accept | Καθορίζει ποιο περιεχόμενο δέχεται ο client |
| Referer | Πηγή από την οποία ήρθε ο client |
| Accept-Encoding | Τι μορφή κωδικοποίησης δέχεται |
| Cookie | Προηγούμενες τιμές για session |

**Response example:**
````http
HTTP/1.1 200 OK
Content-Type: text/html
Set-Cookie: <cookie value>
<website content>
````

## HTTP Verbs
| Verb | Χρήση |
|------|-------|
| GET | Ανάκτηση δεδομένων μέσω Query Parameters |
| POST | Αποστολή δεδομένων στο body του request |
| PUT | Εγγραφή ή ενημέρωση δεδομένων στον server |
| DELETE | Διαγραφή ενός resource |
| PATCH | Ενημέρωση resource με νέα τιμή |

## HTTP Response Codes
| Κωδικός | Σημασία |
|---------|---------|
| 200 | Κανονική απάντηση |
| 301 | Μόνιμη ανακατεύθυνση |
| 302 | Προσωρινή ανακατεύθυνση |
| 400 | Λανθασμένο αίτημα |
| 403 | Απαγορευμένη πρόσβαση |
| 404 | Resource δεν βρέθηκε |
| 500 | Σφάλμα server |

## REST
REST υπηρεσίες χρησιμοποιούν HTTP Verbs και Response Codes. Παράδειγμα URL:
````
http://example.com/users/search/w3schools
````
| Παράμετρος | Σχόλιο |
|------------|--------|
| users | Πρόσβαση στην ενότητα χρηστών |
| search | Χρήση λειτουργίας αναζήτησης |
| w3schools | Ο χρήστης που αναζητείται |

## Sessions & State
HTTP δεν αναγνωρίζει επαναλαμβανόμενους επισκέπτες από μόνο του. Χρησιμοποιούνται cookies ή άλλες μέθοδοι για διατήρηση κατάστασης.
Κοινά cookies:
- PHPSESSID
- JSESSIONID
- ASP.NET_SessionID

Άλλες μέθοδοι client-side:
- JWT (JSON Web Tokens)
- ASP.Net ViewState

## Virtual Hosts (Vhosts)
Ένας server μπορεί να φιλοξενεί πολλές εφαρμογές. Ο server βασίζεται στο Host header για να στείλει το request στη σωστή εφαρμογή.

## URL Encoding
Ασφαλής μεταφορά δεδομένων:
| Χαρακτήρας | Κωδικοποίηση |
|------------|--------------|
| % | %25 |
| space | %20 |
| " | %22 |
Εργαλείο: [CyberChef](https://gchq.github.io/CyberChef/)

## JavaScript
Χρησιμοποιείται για δυναμικό περιεχόμενο και μπορεί να εμπλέκεται σε επιθέσεις σε web εφαρμογές.

## Encryption με TLS
HTTP δεν υποστηρίζει κρυπτογράφηση. Το HTTPS χρησιμοποιεί TLS για ασφαλή μεταφορά δεδομένων (αντικατέστησε το SSL).

