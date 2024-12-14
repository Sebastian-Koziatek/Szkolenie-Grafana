# Szkolenie z Grafany

Witaj w repozytorium szkoleniowym z Grafany! To repozytorium zawiera materiały oraz przykłady, które pomogą Ci w nauce i konfiguracji Grafany – narzędzia do monitorowania i wizualizacji danych.
## Spis treści

  

- [Wstęp](#wstęp)
- [Instalacja](#instalacja)
- [Konfiguracja Grafany](#konfiguracja-grafany)
- [Tworzenie dashboardów](#tworzenie-dashboardów)
- [Dodawanie źródeł danych](#dodawanie-źródeł-danych)
- [Przykłady](#przykłady)
- [Dodatkowe zasoby](#dodatkowe-zasoby)

## Wstęp  

Grafana to jedno z najpopularniejszych narzędzi do wizualizacji danych, które umożliwia monitorowanie infrastruktury IT, aplikacji oraz wszelkich innych źródeł danych. Dzięki grafikom, wykresom i alarmom, Grafana pomaga śledzić wydajność systemu i reagować na potencjalne problemy w czasie rzeczywistym  

![Grafana Logo](https://grafana.com/static/assets/img/grafana_logo.svg)


## Instalacja  

### Krok 1: Instalacja Grafany na systemie Linux (RHEL 9)

1. Zainstaluj repozytorium Grafana:
```bash
sudo dnf install https://packages.grafana.com/oss/rpm/grafana-9.6.0-1.x86_64.rpm
```

2. Uruchom i włącz usługę Grafany:
```bash
sudo systemctl start grafana-server
sudo systemctl enable grafana-server
```

3. Sprawdź status usługi:
```bash
sudo systemctl status grafana-server
```

4. Otwórz przeglądarkę i przejdź do `http://localhost:3000`. Domyślne dane logowania to:
- **Login:** admin
- **Hasło:** admin (po pierwszym logowaniu zostaniesz poproszony o zmianę hasła).

### Krok 2: Instalacja na Dockerze

Jeśli chcesz uruchomić Grafanę w kontenerze Docker, użyj poniższego polecenia:

```bash
docker run -d -p 3000:3000 --name=grafana grafana/grafana:latest
```
## Konfiguracja Grafany
  
Po zainstalowaniu Grafany, czas na jej konfigurację.
### Krok 1: Konfiguracja źródeł danych

Grafana obsługuje wiele źródeł danych, takich jak Prometheus, Elasticsearch, InfluxDB i inne. Aby dodać źródło danych:

1. Zaloguj się do Grafany.
2. Przejdź do **Configuration (Koło zębate)** > **Data Sources**.
3. Kliknij **Add Data Source** i wybierz odpowiedni typ źródła danych (np. **Prometheus**).
4. Wprowadź niezbędne dane konfiguracyjne (adres serwera, port, itd.).
### Krok 2: Tworzenie dashboardów  

Po dodaniu źródła danych możesz zacząć tworzyć dashboardy.

1. Kliknij **Create (Plus)** > **Dashboard**.
2. Dodaj nowe panele klikając **Add Panel**.
3. Wybierz typ panelu (np. wykres, tabela, itp.) i skonfiguruj zapytanie w zależności od wybranego źródła danych.
## Przykłady  

### Wykres z Prometheusa

```bash
avg(rate(node_cpu_seconds_total{mode="idle"}[5m])) by (instance)
```

Powyższe zapytanie oblicza średnią wartość z wykorzystania CPU dla poszczególnych instancji w ciągu ostatnich 5 minut.
