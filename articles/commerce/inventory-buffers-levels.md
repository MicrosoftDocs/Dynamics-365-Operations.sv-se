---
title: Konfigurera inventeringsbuffertar and lagernivåer
description: I det här avsnittet beskrivs hur du konfigurerar lagerkvantiteter och lagernivåer som bestämmer hur meddelanden om lager tillgänglighet kan anges på Microsoft Dynamics 365 Commerce-webbplatser.
author: boycezhu
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: ef58dbb756c7bed3924010cb33eff27af66cd0bd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415860"
---
# <a name="configure-inventory-buffers-and-inventory-levels"></a>Konfigurera inventeringsbuffertar and lagernivåer

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar lagerkvantiteter och lagernivåer som bestämmer hur meddelanden om lager tillgänglighet kan anges på Microsoft Dynamics 365 Commerce-webbplatser.

## <a name="overview"></a>Översikt

Dynamics 365 Commerce huvudkontoret innehåller lagerdata och olika kanaler som kassaapplikationer, näthandelsbutiker och andra anpassade integrerade applikationer som drar och skjuter omkring inventering på ett asynkront sätt. Därför är de tillgängliga lagervärden som hämtas via sidan för lagerbehållning i Commerce-administration via kassaanvändargränssnittet och via näthandelslager. API:er för lagertillgänglighet är inte alltid 100 procent korrekt i realtid.

I stället för att visa faktiska lagervärden i näthandelsbutiker föredrar många återförsäljare bara att visa meddelanden om lagertillgänglighetsstatus (t.ex. "tillgänglig" eller "på lagret") för att informera kunderna om huruvida en artikel är tillgänglig för inköp eller eventuellt inte kan användas i lager. För den här metoden måste lagerkvantiteter och lagernivåer som fastställer lagertillgänglighet meddelanden göras tillgängliga och konfigurerade.

## <a name="prerequisite-turn-on-the-inventory-buffers-and-inventory-levels-feature"></a>Förutsättning: aktivera funktionen lagerbuffrar och lagernivåer

Funktionen för lagerbuffrar och lagernivåer styrs via funktionshantering i Commerce-administration. Så här aktiverar du funktionen anpassning.

1. Gå till **Systemadministration** \> **Arbetsytor** \> **Funktionshantering**.
1. Sök efter funktionen **Aktivera lagerbuffrar och lagernivåer**, markera raden och välj sedan **Aktivera nu**.

När funktionen är aktiverad kan du söka efter lagernivåer vid **Retail och Commerce \> Lagerhantering**.

## <a name="create-and-configure-an-inventory-level-profile"></a>Skapa och konfigurera en lagernivåprofil

En *lagernivåprofil* avgör om en given kvantitet i en produktkvantitetstatus tas med i lager, utanför lagret eller någon annan anpassad status. Du kan skapa och konfigurera flera lagernivåprofiler per juridisk person. Varje profil består av en uppsättning lagernivåer och varje nivå definieras av ett *intervall*, en *kod* och en *etikett*.

- **Intervall** – varje intervall definieras av en *startkvantitet* och en *slutkvantitet*. Ett värde för kvantitet ligger i ett intervall om det är mer än startkvantiteten för intervallet och inte mer än slutkvantiteten.
- **Kod** – en kod är en intern förkortning som representerar nivån. Kunder som direkt integrerar med lager-API:er kan använda koder för att skapa ytterligare logik för en given lagernivå. De kan till exempel stänga av inköpsmöjligheterna för en produkt när lagernivåkoden är **OOS** ("slut på lagret").
- **Etikett** – en etikett är ett meningsfullt kund riktat meddelande som förmedlar en lager nivå till kunder på en näthandelsplats.

### <a name="create-an-inventory-level-profile"></a>Skapa en lagernivåprofil

Skapa en lagernivåprofil enligt följande instruktioner.

1. Gå till  **Retail och Commerce** \> **Lagerhantering** \> **Lagernivåer**.
1. I åtgärdsfönstret välj **Ny** och ange sedan värden i fälten **Profil-ID** och **Beskrivning**.
1. På snabbfliken **Intervall** välj **Lägg till** om du vill lägga till en ny nivå och anger sedan värden i kolumnerna **startkvantitet**, **slutkvantitet**, **kod** och **etikett** för den nivån. Upprepa detta steg för att lägga till fler nivåer. Efter behov kan du redigera värdena i rutnätet eller välja **ta bort** om du vill ta bort en nivå.
1. Klicka på **Spara** i åtgärdsfönstret.

När en ny profil skapas initieras två lagernivåer automatiskt:

- **OOS** – nivån "på lagret", där den nedre gränsen för intervallet är negativ oändlighet. Startkvantiteten och koden kan inte redigeras för den här nivån.
- **AVAIL** – "tillgänglig" nivå, där den övre gränsen för intervallet är oändlig. Slutkvantiteten och koden kan inte redigeras för den här nivån.

> [!NOTE]
> Det får inte finnas luckor eller överlappningar mellan intervall i profildefinitionen.

Du kan använda knappen **översättningar** i åtgärdsfönstret för att konfigurera lokaliserade strängar för etikettmeddelandet. Du måste sedan köra **1110** (**Global konfiguration**) distributionsschema för att synkronisera de lokaliserade strängarna till kanaler.

### <a name="configure-an-inventory-level-profile"></a>Konfigurera en lagernivåprofil

Du kan konfigurera en lagernivåprofil på antingen produktkategorinivå eller enskild produktnivå. När en lagernivåprofil konfigureras för en produkt, bestäms lagernivån baserat på de intervall som har definierats i den länkade profilen. I annat fall bestäms lagernivån "tillgänglig" eller "slut på lager" utifrån om produkten har en positiv lagerbehållning.

Följ dessa steg för att konfigurera en lagernivåprofil för en kategori.

1. Gå till **Retail och Commerce** \> **Produkter och kategorier** \> **Produkthierarki och handel**.
1. Välj kategori för att konfigurera en lagernivåprofil för.
1. På snabbfliken **Sälj produktegenskaper** välj juridisk person.
1. I avsnitt **lagertillgänglighet för handel** i fält **Lagernivåprofil**, välj en av de fördefinierade lagerprofiler.

Du kan använda knappen **Uppdatera produkter** i åtgärdsfönstret för att sprida värdet på kategorinivåprofilen till kategorins underliggande produkter. Mer information finns i [Hantera produktkategorier och produkter](category-management-product-creation.md).

Följ dessa steg för att konfigurera en lagernivåprofil för frisläppt produkt.

1. Gå till **Retail och Commerce** \> **Produkter och kategorier** \> **Frisläppta produkter efter kategori**.
1. Välj en produkt och öppna sedan sidan produktinformation.
1. Snabbfliken **Sälj** i avsnittet **lagertillgänglighet för handel** i fältet **Lagernivåprofil** välj en av de fördefinierade lagerprofiler.

När en ny produkt skapas fältet **Lagernivåprofil** som många andra produktnivåattribut kommer att ställas in på värdet som är konfigurerat för den kategori som produkten är associerad med.

> [!NOTE]
> Lagernivåprofilen är ett attribut som bara är ett juridiskt entitet. För samma kategori eller produkt kan lagernivåprofil för lagernivån variera mellan juridiska personer.

Om du vill synkronisera konfigurationerna för lagernivåprofiler till kanaler följer du dessa steg.

1. Gå till **Butik och handel** \> **Butik och handel-IT** \> **Distributionsschema**.
1. Kör **1040** (**Produkt**) distributionsschema.

## <a name="configure-an-inventory-buffer"></a>Konfigurera en lagerkvantitet

*Lagerkvantiteten* är ett användardefinierat värde som subtraherar den ytterligare kvantiteten av en artikel från den ursprungliga kvantiteten för att beräkna den uppskattade kvantiteten. Denna uppskattade kvantitet ger detaljister en säker buffert så att de inte säljer en produkt genom att sälja mer än den faktiska lagerbehållningen. Du kan konfigurera en lagerbuffert på antingen produktkategorinivå eller enskild produktnivå. Om ingen lagringsbuffert anges är standardvärdet för **0** (noll) används.

Följ dessa steg för att konfigurera en lagerbuffer för en kategori.

1. Gå till **Retail och Commerce** \> **Produkter och kategorier** \> **Produkthierarki och handel**.
1. Välj kategori för att konfigurera en lagerbuffer för.
1. På snabbfliken **Sälj produktegenskaper** välj juridisk person.
1. I avsnittet **lagertillgänglighet för handel** i fältet **lagerkvantitet** ange positivt värde.

Du kan använda knappen **Uppdatera produkter** i åtgärdsfönstret för att sprida värdet på kategorinivåbuffer till kategorins underliggande produkter. Mer information finns i [Hantera produktkategorier och produkter](category-management-product-creation.md).

Följ dessa steg för att konfigurera en frisläppt produkt för en kategori.

1. Gå till **Retail och Commerce** \> **Produkter och kategorier** \> **Frisläppta produkter efter kategori**.
1. Välj en produkt och öppna sedan sidan produktinformation.
1. I snabbfliken **Sälj** i **lagertillgänglighet för handel** i fältet **lagerkvantitet** ange positivt värde.

När en ny produkt skapas fältet **Lagerbuffer** som många andra kommer att ställas in på värdet som är konfigurerat för den kategori som produkten är associerad med.

> [!NOTE]
> Om profilerna för lagerkvantitet och lagernivå har konfigurerats för en produkt, kommer produktens beräknade kvantitet (dvs. den ursprungliga kvantiteten minusvärdet för buffer) att användas för intervallberäkning för att fastställa lagernivån.

Om du vill synkronisera konfigurationerna för inventeringsbuffertar till kanaler följer du dessa steg.

1. Gå till **Butik och handel** \> **Butik och handel-IT** \> **Distributionsschema**.
1. Kör **1040** (**Produkt**) distributionsschema.

## <a name="use-inventory-buffers-and-inventory-levels-in-e-commerce-scenario"></a>Använda lagerkvantiteter och lagernivåer i handelsscenario

I Commerce webbplatsskaparen används funktionerna för lagerkvantitet och lager nivå i Commerce-administration för att fastställa meddelanden om lagertillgänglighet på näthandelsplatser. Mer information om [Använd lagerinställningar](inventory-settings.md).

Alternativt, om du integrerar med en tredjeparts näthandelslösning, kan du använda **GetEstimatedAvailability** och **GetEstimatedProductWarehouseAvailability** API:er för att visa lagertillgängligheten för en produkt i ditt näthandelsscenario. Mer information om dessa API:er finns i [Beräkna lagerdisposition för butikskanaler](calculated-inventory-retail-channels.md).

Introduktionen av lagerkvantiteter och lagernivåer gör att dessa API:er kan returnera lagernivåkoder och etikettmeddelanden som bestäms baserat på totala tillgängliga och tillgängliga fysiska värden. API:erna kan konfigureras ytterligare för att avgöra om lagerkvantiteten returneras tillsammans med meddelandet och om den disponibla kvantiteten reduceras med lagervärdet.

Konfigurera svaret på produkttillgänglighet API:erna enligt följande instruktioner.

1. Öppna **Retail och Commerce** \> **Administrationsinställning** \> **Parametrar** \> **Commerce-parametrar**.
1. I avsnittet **Butikslager** på fliken **Lager** i fältet **Produkttillgänglighet API:er för näthandel** välj ett värde.
1. Om du vill tillämpa inställningarna på kanaler kör du **1110** (**Globalkonfiguration**) distributionschemajobb.

## <a name="additional-resources"></a>Ytterligare resurser

[Hantera produktkategorier och produkter](category-management-product-creation.md)

[Använd lagerinställningar](inventory-settings.md)

[Beräkna lagertillgänglighet för butikskanaler](calculated-inventory-retail-channels.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]