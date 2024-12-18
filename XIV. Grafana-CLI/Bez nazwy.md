# Grafana-CLI Zastosowania

  

## 1. Sprawdzanie wersji Grafana:

Sprawdzanie wersji zainstalowanej Grafany.

```
grafana-cli -v
```

## 2. Uaktualnienie samego narzędzia `grafana-cli`:

Aktualizacja samego narzędzia `grafana-cli` w celu poprawienia jego funkcji.

```
grafana-cli update
```

## 3. Sprawdzanie dostępnych pluginów:

Wyszukiwanie dostępnych pluginów w oficjalnym repozytorium Grafany.

```
grafana-cli plugins list-available
```

## 4. Instalowanie pluginów z plików lokalnych:

Możesz zainstalować pluginy nie tylko z repozytorium, ale także z pliku lokalnego (np. jeśli masz własny plugin do Grafany).

```
grafana-cli plugins install /ścieżka/do/pluginu.zip
```

## 5. Aktualizacja pojedynczego pluginu:

Aktualizowanie zainstalowanego pluginu do najnowszej wersji.

```
grafana-cli plugins update plugin-name
```
## 6. Zainstalowanie wtyczki w trybie nieinteraktywnym (skrypt):

Jeżeli chcesz zainstalować wtyczki bez interakcji użytkownika, np. w automatycznych skryptach.

```
grafana-cli plugins install plugin-name --no-sudo
```

## 7. Usuwanie wtyczki:

Usuwanie pluginu, który już nie jest potrzebny.

```
grafana-cli plugins uninstall plugin-name
```
## 8. Listowanie zainstalowanych pluginów:

Lista wszystkich zainstalowanych pluginów w Grafanie.

```
grafana-cli plugins list-installed
```
## 9. Sprawdzanie dostępnych wersji pluginu:

Możesz sprawdzić, jakie wersje są dostępne dla danego pluginu w repozytorium.

```
grafana-cli plugins list-available plugin-name
```

## 10. Instalowanie pluginów z GitHub lub z URL:

Możesz zainstalować pluginy z repozytoriów GitHub, podając odpowiedni URL.

```
grafana-cli plugins install <url-do-pluginu-z-githuba>
```