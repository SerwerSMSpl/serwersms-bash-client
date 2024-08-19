# SerwerSMS.pl Bash Client API
Klient Bash do komunikacji zdalnej z API v2 SerwerSMS.pl z poziomu terminala.

Zalecane jest, aby komunikacja przez HTTPS API odbywała się z loginów utworzonych specjalnie do połączenia przez API. Konto użytkownika API można utworzyć w Panelu Klienta → Ustawienia interfejsów → HTTP API → Użytkownicy API.

## Konfiguracja
Dane autoryzacyjne należy zdefiniować w pliku serwersms, przykładowo:
```bash
USERNAME="demo"
PASSWORD="demo"
```
## Przykładowe wywołania
Poniżej zawarta jest lista przykładowych wywołań do API.
#### Wysyłka SMS ECO
```bash
$ ./serwersms messages/send_sms --phone "500600700" --text "Test message" --details true
```

#### Wysyłka SMS FULL
```bash
$ ./serwersms messages/send_sms --sender INFORMACJA --phone "500600700" --text "Test message" --details true --utf true
```

#### Wysyłka spersonalizowanych SMS
```bash
$ ./serwersms messages/send_personalized --sender INFORMACJA --messages "500600700:Test message 1]|[600700800:Test message 2" --details true --utf true
```

#### Wysyłka VOICE
```bash
$ ./serwersms messages/send_voice --phone "500600700" --test true --text "Test message" --details true
```

#### Pobieranie raportów doręczeń
```bash
$ ./serwersms messages/reports
```

#### Pobieranie wiadomości przychodzących
```bash
$ ./serwersms messages/recived --type "eco"
```

#### Zapis grupy
```bash
$ ./serwersms groups/add --name "My group"
```

#### Zapis kontaktu
```bash
$ ./serwersms contacts/add --phone "500600700" --group_id 17327005 --first_name "My firstname"
```

#### Listowanie kontaktów
```bash
$ ./serwersms contacts/index --search "500600700"
```

#### Pobranie faktury
```bash
$ ./serwersms payments/invoice --id 47957 --facture "faktura.pdf"
```

#### Wyszukanie numeru na czarnej liście
```bash
$ ./serwersms blacklist/index --phone "500600700"
```

#### Sprawdzenie numeru HLR
```bash
$ ./serwersms phones/check --phone "500600700"
```

#### Zapis subkonta
```bash
$ ./serwersms subaccounts/add --subaccount_username "username" --subaccount_password "my_password" --subaccount_id 4563
```

## Dokumentacja
Lista wszystkich metod oraz opcji dostępna jest pod adresem http://dev.serwersms.pl Należy pamiętać o tym, aby parametry tekstowe w wywołaniu osadzić w znakach "".

## Konsola API
http://apiconsole.serwersms.pl/
