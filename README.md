# categorization-program
GitHub Projekt Kategorizáló F# nyelven
Ez a program a GitHub REST API-t használja. A lekérdezésekhez személyes hozzáférési tokenre (Personal Access Token - PAT) lesz szükséged, különben nagyon gyorsan eléri a lekérdezési sebességkorlátot (rate limit).

1. Előkészületek: GitHub Personal Access Token (PAT)
Látogass el a GitHubra: https://github.com/settings/tokens
Kattints a "Generate new token" vagy "Generate new token (classic)" gombra.
Adj neki egy informatív nevet (pl. "FSharpCategorizerToken").
A jogosultságoknál (scopes) elegendő, ha csak a public_repo (vagy repo ha privát repo-kat is akarsz lekérdezni) és read:org (ha szervezeteken belüli repo-kat is lekérdeznél) opciót pipálod be.
Generáld a tokent, és másold ki azonnal, mert később nem fogod tudni újra megtekinteni!
2. Projekt Létrehozása
Nyiss meg egy terminált, és hozz létre egy új F# konzolalkalmazást, majd lépj be a könyvtárba:

Bash

dotnet new console -lang F# -n GithubProjectCategorizer
cd GithubProjectCategorizer
3. Függőségek Hozzáadása
Szükségünk lesz egy HTTP kliensre a GitHub API hívásához és egy JSON deszerializáló könyvtárra. A Newtonsoft.Json egy népszerű választás .NET-ben.

Bash

dotnet add package FSharp.Json
dotnet add package Http.fs
4. A Program Kódja (Program.fs)
