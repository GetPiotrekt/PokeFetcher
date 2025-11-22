## To repozytorium zawiera dokumentację również w języku polskim, która znajduje się poniżej.

# EN / REST API – Pokémon Data Fetching System

This project implements a simple client–server application that retrieves and processes Pokémon information using the public PokeAPI REST API, enabling communication between a custom Java server and client over TCP.

# 🚀 Features

	•   Fetch Pokémon Data: The server retrieves detailed Pokémon information from the public PokeAPI using the GET /pokemon/{name} endpoint.
	•	Custom Server–Client Communication: The application includes a simple TCP-based server that handles requests from a custom-built client.
	•	Formatted Responses: Server converts raw JSON from PokeAPI into user-friendly text.
	•	Request/Response Handling: The client sends requests and receives full API responses through buffered communication.
	•	Error Handling: The system detects connection issues, invalid requests, and API errors.

# 📋 Requirements

## Functional Requirements
	1. Retrieve Pokémon Data
	•	The server must fetch Pokémon information from https://pokeapi.co/api/v2/pokemon/{name}.
	•	The response must include full JSON data received from the API.
   
	2. Handle Client Requests
	•	The client must be able to send a request string to the server.
	•	The server must read, interpret, and process incoming requests.
	•	Valid request example: GET /pokemon/ditto.
   
	3. Return Formatted Responses
	•	The server must return processed and readable Pokémon information.
	•	The client must display the server’s response to the user.
   
	4. Networking
	•	The server must listen on port 13612.
	•	The client must connect to the server via localhost:13612.
   
	5. Error Reporting
	•	The system must notify the user when:
	•	The Pokémon does not exist.
	•	The API request fails.
	•	The request format is invalid.
	•	The server is unreachable.

## Non-Functional Requirements
	1. Reliability
	•	The server should handle incorrect or malformed requests gracefully.
	•	The application should not crash on API or network failures.
   
	2. Performance
	•	Responses should be fetched and returned without noticeable delay.
	•	Network communication should remain efficient using buffered I/O.
   
	3. Maintainability
	•	Clear separation of responsibilities between the server, client, and API methods.
	•	Methods such as fetchDataFromApi() and formatApiResponse() must remain modular.
   
	4. Security
	•	External communication with PokeAPI must use HTTPS.
	•	The system should avoid exposing unnecessary server details.
   
	5. Portability
	•	The server and client should run on any system supporting Java and TCP/IP.

# 🧩 Architecture

The system follows a simple Client–Server architecture:
## Client <──TCP──> Server <──HTTP/HTTPS──> PokeAPI

## Server Responsibilities
	•	Accept client connections.
	•	Process requests such as GET /pokemon/{name}.
	•	Call helper functions:
	•	fetchDataFromApi(apiUrl) — retrieves raw API data.
	•	formatApiResponse(apiResponse) — converts JSON to readable output.
	•	Return the formatted response to the client.

## Client Responsibilities
	•	Connect to the server via TCP.
	•	Send requests using:
	•	sendRequest(writer, request)
	•	Receive responses using:
	•	receiveResponse(reader)
	•	Display the received data to the user.

# 🔧 Technologies
	•	Java: core language for both server and client.
	•	TCP/IP Sockets: communication between client and server.
	•	HTTP / HTTPS: communication between server and PokeAPI.
	•	PokeAPI (public REST API): source of Pokémon data.
	•	BufferedReader / BufferedWriter: for efficient request/response handling.

**────────────────────────**

# PL / REST API – System Pobierania Danych o Pokemonach

Projekt implementuje prostą aplikację klient–serwer, która pobiera i przetwarza informacje o Pokemonach korzystając z publicznego PokeAPI REST API, umożliwiając komunikację między własnym serwerem w Javie a klientem za pomocą TCP.

# 🚀 Features
	•   Pobieranie danych o Pokemonach: Serwer pobiera szczegółowe informacje o Pokemonach z publicznego PokeAPI używając endpointu GET /pokemon/{name}.
	•	Komunikacja klient–serwer: Aplikacja zawiera prosty serwer TCP obsługujący żądania od własnego klienta.
	•	Formatowanie odpowiedzi: Serwer przekształca surowy JSON z PokeAPI w czytelny tekst dla użytkownika.
	•	Obsługa żądań i odpowiedzi: Klient wysyła żądania i odbiera pełne odpowiedzi API przez buforowany strumień.
	•	Obsługa błędów: System wykrywa problemy z połączeniem, niepoprawne żądania i błędy API.

# 📋 Wymagania

## Wymagania funkcjonalne
    1. Pobieranie danych o Pokemonach
    •	Serwer musi pobierać informacje o Pokemonach z https://pokeapi.co/api/v2/pokemon/{name}.
    •	Odpowiedź musi zawierać pełny JSON otrzymany z API.

    2. Obsługa żądań klienta
    •	Klient musi móc wysyłać ciąg znaków z żądaniem do serwera.
    •	Serwer musi odczytać, zinterpretować i przetworzyć nadchodzące żądania.
    •	Przykład prawidłowego żądania: GET /pokemon/ditto.

    3. Zwracanie sformatowanych odpowiedzi
    •	Serwer musi zwracać przetworzone i czytelne informacje o Pokemonie.
    •	Klient musi wyświetlić odpowiedź serwera użytkownikowi.

    4. Komunikacja sieciowa
    •	Serwer musi nasłuchiwać na porcie 13612.
    •	Klient musi łączyć się z serwerem poprzez localhost:13612.

    5. Obsługa błędów
    •	System musi powiadamiać użytkownika, gdy:
    •	Pokemon nie istnieje.
    •	Żądanie do API się nie powiodło.
    •	Format żądania jest niepoprawny.
    •	Serwer jest niedostępny.

## Non-Functional Requirements
    1. Niezawodność
    •	Serwer powinien prawidłowo obsługiwać niepoprawne lub źle sformułowane żądania.
    •	Aplikacja nie powinna ulegać awarii w przypadku błędów API lub sieci.

    2. Wydajność
    •	Odpowiedzi powinny być pobierane i zwracane bez zauważalnego opóźnienia.
    •	Komunikacja sieciowa powinna być efektywna dzięki buforowanemu I/O.

    3. Utrzymanie
    •	Czysty podział odpowiedzialności między serwerem, klientem i metodami API.
    •	Metody takie jak fetchDataFromApi() i formatApiResponse() muszą pozostać modułowe.

    4. Bezpieczeństwo
    •	Komunikacja z PokeAPI musi korzystać z HTTPS.
    •	System powinien unikać ujawniania niepotrzebnych informacji o serwerze.

    5. Przenośność
    •	Serwer i klient muszą działać na każdym systemie obsługującym Javę i TCP/IP.

# 🧩 Architecture

System oparty jest o prostą architekturę klient–serwer:
## Klient <──TCP──> Serwer <──HTTP/HTTPS──> PokeAPI

## Obowiązki serwera
    •	Obsługa połączeń od klientów.
    •	Przetwarzanie żądań typu GET /pokemon/{name}.
    •	Wywoływanie funkcji pomocniczych:
    •	fetchDataFromApi(apiUrl) — pobiera surowe dane z API.
    •	formatApiResponse(apiResponse) — konwertuje JSON na czytelny tekst.
    •	Zwracanie sformatowanej odpowiedzi klientowi.

## Obowiązki klienta
    •	Łączenie się z serwerem przez TCP.
    •	Wysyłanie żądań za pomocą:
    •	sendRequest(writer, request)
    •	Odbieranie odpowiedzi za pomocą:
    •	receiveResponse(reader)
    •	Wyświetlanie odebranych danych użytkownikowi.

# 🔧 Technologie
    •	Java: główny język dla serwera i klienta.
    •	TCP/IP Sockets: komunikacja między klientem a serwerem.
    •	HTTP / HTTPS: komunikacja między serwerem a PokeAPI.
    •	PokeAPI (publiczne REST API): źródło danych o Pokemonach.
    •	BufferedReader / BufferedWriter: efektywna obsługa żądań i odpowiedzi.
