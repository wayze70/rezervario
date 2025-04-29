# 🗓️ Rezervario

**Rezervario** je webová aplikace určená pro správu rezervací. Umožňuje vytváření, správu a přehledné zobrazení rezervací pro různé typy služeb a akcí.

Aplikace běží online na adrese:  
🔗 [https://www.rezervario.cz](https://www.rezervario.cz)

# DEMO Účty

Pro snadnější vyzkoušení aplikace jsem připravil sadu demo účtů.  
Pro lepší představu si můžeme představit, že vytvořený účet patří podnikateli (např. Josefu Novákovi), který vlastní více společností zaměřených na různé služby:

- **Kurzy programování**  
  Zákazníci se mohou rezervovat na adrese:  
  [https://www.rezervario.cz/rezervace/kurz-programovani](https://www.rezervario.cz/rezervace/kurz-programovani)

- **Skupinové silové tréninky v posilovně**  
  Tréninky jsou dostupné veřejnosti na adrese:  
  [https://www.rezervario.cz/rezervace/skupinove-cviceni](https://www.rezervario.cz/rezervace/skupinove-cviceni)

- **Rezervace sportovní haly + turnaje**  
  Možnost rezervace sportovní haly jsou dostupné veřejnosti na adrese:  
  [https://www.rezervario.cz/rezervace/sportovni-hala](https://www.rezervario.cz/rezervace/sportovni-hala)

## Přihlášení do aplikace

Pro přístup do demo účtů použijte následující přihlašovací údaje:

- **E-mail**: `demo@rezervario.cz`
- **Heslo**: `123456`*(heslo je možné mít u každé organizace nastavené jinak, pokud podnikatel spravuje více organizací)*

Po přihlášení si jednoduše vyberte organizaci, ke které se chcete připojit, podle zaměření popsaného výše.

---

## 🚀 Lokální spuštění

Pro správné spuštění projektu lokálně je potřeba:
1. Naklonovat repozitář.
2. Nakonfigurovat soubor `appsettings.json` v projektu `Reservation.Api` podle níže uvedeného příkladu.
3. Upravit adresu API v souboru `Reservation.Web.Client/CustomExtensions/Constants.cs` – změňte hodnotu `ApiBaseAddress` podle toho, kde vám běží API.
4. Spustit migrační skripty databáze.
5. Spustit backend a frontend. (BE je možné spustit v dockeru)

### Příklad `appsettings.json`

```json
{
  "AllowedHosts": "*",
  "ConnectionStrings": {
    "DefaultConnection": "Host=localhost;Port=5432;Database=db;Username=username;Password=secretpassword"
  },
  "Jwt": {
    "Key": "your256BitSecretKeyYour256BitSecretKeyYour256BitSecretKey",
    "Issuer": "yourIssuer",
    "Audience": "yourAudience"
  },
  "FrontendUrl": "https://localhost:port",
  "BackendUrl": "https://localhost:port",
  "EmailSettings": {
    "SenderEmail": "example@domain.com",
    "SmtpPassword": "yourSmtpPassword"
  }
}
```

> ⚠️ **Poznámka:**  
> Hodnota `Jwt:Key` musí mít minimálně 256 bitů (tj. 32 bytů).

---

## 🧩 Požadavky

- .NET 8 SDK
- PostgreSQL
- SMTP server pro odesílání e-mailových notifikací  

---

## ⚙️ Použité technologie

- ASP.NET Core Web API (.NET 8)  
- Entity Framework Core  
- PostgreSQL  
- JWT (JSON Web Token)  
- SMTP pro e-mailové notifikace  
- Docker (volitelné)  
- Blazor WebAssembly

---

## 📌 Autor

Vyvinuto jako součást bakalářské práce  
Autor: Michal Syřiště
Vedoucí práce: Mgr. Vojtěch Vorel, Ph.D.  
Fakulta informatiky a managementu, Univerzita Hradec Králové  
