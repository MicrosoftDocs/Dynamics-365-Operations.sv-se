---
title: Produkt- och kundsökning i POS
description: Det här avsnittet innehåller en översikt över de förbättringar som har gjorts i produkt- och kundsökfunktionen i Dynamics 365 Commerce.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 03/10/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: 23b556e72e1ec76be48336bed21d02abd9d31087
ms.sourcegitcommit: db9b35ce6968cad8874b3c13d4c02d84e2617c8b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/11/2021
ms.locfileid: "5574729"
---
# <a name="product-search-and-customer-search-in-the-point-of-sale-pos"></a>Produkt- och kundsökning i POS

[!include [banner](includes/banner.md)]

Modern kassa (Modern Point Of Sale, eller MOPS) samt molnbaserad kassa (Cloud Point Of Sale, eller CPOS) ger en lättanvänd sökfunktion för att snabbt söka efter produkter och kunder. Eftersom sökfältet alltid finns överst i fönstrena MOPS och CPOS kan personalen snabbt söka produkter och kunder.

Medarbetare kan söka efter produkter i sortimentet och kataloger som hör till den aktuella butiken. De kan också söka efter produkter i sortimentet och kataloger som hör till alla andra butiker i företaget. Därför kan kassörerna sälja och returnera produkter utanför butikens sortiment. Medarbetare kan dessutom söka efter kunder som är associerade med den aktuella butiken eller andra butiker i företaget. Medarbetare kan dessutom söka efter kunder som är kopplade till ett annat företag i moderorganisationen.

## <a name="product-search"></a>Produktsökning

Som standard utförs en produktsökning på butikssortimentet. Denna typ av sökning kallas en *lokal produktsökning*. Medarbetare kan emellertid enkelt växla till valfri katalog som är kopplad till den aktuella butiken, eller också söka i en annan butik. Denna typ av sökning kallas en *fjärrproduktsökning*. Välj knappen **Kategorier** till vänster på sidan för att byta katalog. Överst i fönstret som visas väljer du knappen **Ändra katalog** och väljer sedan en av de tillgängliga katalogerna för att titta på den. Systemet söker den valda katalogen för produkter.

På sidan **Ändra katalog** kan personalen enkelt välja valfri butik, eller också kan de söka efter produkter i alla butiker.

![Ändra katalogen](./media/Changecatalog.png "Ändra katalogen")

En lokal produktsökning söker inom följande produktegenskaper:

- Produktnummer
- Produktnamn
- beskrivning
- Dimensioner
- Streckkod
- Söknamn

### <a name="additional-local-product-search-capabilities"></a>Ytterligare sökfunktioner för lokal produkt

- För flera nyckelordssökningar (det vill säga, för sökningar med sökvillkor) kan återförsäljare ange om sökresultatet ska innehåll resultat som matchar *alla* sökord eller endast resultat som matchar *alla* sökord. inställningen för denna funktion finns i kassafunktionens profil, i en ny grupp som heter **Produktsökning**. Standardinställningen är **Matcha alla sökord**. Detta är också den rekommenderade inställningen. När inställningen **Matcha alla sökord** används returneras alla produkter som helt eller delvis matchar ett eller flera sökord som resultat. Resultaten sorteras automatiskt i stigande ordning efter produkter som har de flesta nyckelordsträffarna (helt eller delvis).

    Inställningen **Matcha alla sökvillkor** returnerar endast produkter som matchar alla söktermer (helt eller delvis). Denna inställning är praktisk när produktnamnen är långa och medarbetarna endast vill visa begränsade produkter i sökresultaten. Denna typ av sökning har emellertid två begränsningar:

    - Sökningen utförs på individuella produktegenskaper. Exempelvis returneras bara produkter som har de sökta nyckelorden i minst en produktegenskap.
    - Dimensioner genomsöks inte.

- Återförsäljare kan konfigurera produktsökningen så att denna visar sökförslag när användarna skriver produktnamn. En ny inställning för denna funktion finns i kassafunktionens profil, i en grupp som heter **Produktsökning**. Inställningen kallas **Visa sökförslag medan du skriver**. Denna funktion hjälper anställda att snabbt hitta den produkt som de söker efter, detta eftersom de inte behöver skriva hela namnet manuellt.
- Sökalgoritmen för produkten söker nu också efter de sökta villkoren i produktens **Söknamn**-egenskap.

![Produktförslag](./media/Productsuggestions.png "Produktförslag")

## <a name="customer-search"></a>Sök efter kund

Kundsök används för att hitta kunder för olika ändamål. Kassörer kan exempelvis visa en kunds önskelista eller inköpshistorik, eller lägga till kunden i en transaktion. Sökalgoritmen matchar sökvillkoren mot de värden som finns i följande kundegenskaper:

- Namn
- E-postadress
- Telefonnummer
- Förmånskortnummer
- Adress
- Kontonummer

Bland dessa egenskaper ger namnet den mesta flexibiliteten för sökningar med flera nyckelord eftersom algoritmen returnerar alla kunder som matchar något av de söknyckelord som du söker. De kunder som matchar de flesta nyckelorden visas överst i resultatet. Detta beteende hjälper kassörerna i situationer där sökningen sker genom att skriva det fullständiga namnet, men efternamn och förnamn har växlas under den första datainmatningen. Av prestandaskäl har dock alla andra egenskaper bevarat ordningen för nyckelorden i sökningen. Därför returneras inga resultat om ordningen på nyckelorden för sökningen inte matchar den ordning som data lagras i.

En kundsökning utförs som standard på kund-adressböcker kopplade till butiken. Denna typ av sökning kallas en *lokal kundsökning*. Medarbetare kan emellertid också söka efter kunder globalt. Med andra ord kan man söka i samtliga företagets butiker och mellan alla juridiska personer. Denna typ av sökning kallas en *fjärrkundsökning*.

För att genomföra en global sökning kan personalen använda knappen **Filtrera resultat** längst ned på sidan och sedan alternativet **Sök alla butiker** som visas på bilden nedan. I detta fall returneras inte bara kunder. Alla typer av parter som ingår i en adressbok på huvudkontoret returneras också. Dessa parter inkluderar medarbetare, leverantörer, kontakter och konkurrenter.

> [!NOTE]
> Minst fyra tecken måste anges för en fjärrkundsökning för att denna ska returnera resultat.

Kund ID som frågas för kunder från andra juridiska personer, detta eftersom inget kund-ID har skapats för dessa parter i det aktuella företaget. Om en medarbetare emellertid öppnar sidan för information om kunden kan systemet automatiskt skapa ett kund-ID för parten, och kopplar också ihop butikens kundadressböcker med kunden. Därför syns kunden i lokala butikssökningar som utförs senare.

![Global kundsökning](./media/Globalcustomersearch.png "Global kundsökning")

### <a name="additional-local-customer-search-capabilities"></a>Ytterligare sökfunktioner för lokal kund

När användaren söker efter ett telefonnummer ignorerar systemet specialtecken såsom blanksteg, bindestreck och parenteser som kan ha lagts till när kunden skapades. Därför behöver kassörerna inte ta hänsyn till telefonnummerformatet när de söker. Om ett kundtelefonnummer exempelvis angetts som **123-456-7890**, kan en kassör söka efter kunden genom att skriva in **1234567890**, eller genom att ange de första siffrorna i telefonnumret.

> [!NOTE]
> En kund kan ha flera telefonnummer och flera e-postadresser. Kundens sökalgoritm söker också igenom dessa sekundära e-postadresser och telefonnummer, men sidan med sökresultat för kund visar endast primär e-postadress och telefonnummer. Detta kan leda till en del förvirring när det returnerade kundresultatet inte visar den sökta e-postadressen eller telefonnumret. I en senare version planerar vi att förbättra skärmen för kundens sökresultat för att visa den här informationen.

Vanlig kundsökning kan vara tidskrävande, eftersom den söker över flera fält. Kassörer kan istället söka i en kudegenskap, till exempel namn, telefonnummer eller e-postadress. Egenskaper som kundens sökalgoritm använder kallas *sökvillkor för kund*. Systemadministratören kan enkelt konfigurera ett eller flera kriterier som genvägar som visas i POS. Eftersom sökningen är begränsat till ett enda villkor visas endast relevanta sökresultat och den får mycket bättre prestanda än en standardkundsökningsprestanda. I följande illustration visas kundens sökgenvägar i POS.

![Genvägar för kundsökning](./media/SearchShortcutsPOS.png "Genvägar för kundsökning")

Om du vill ange sökvillkor som genvägar måste administratören öppna sidan **Handelparametrar** i Commerce och sedan på fliken **Sökvillkor för kassa** väljer du de kriterier som ska visas som genvägar.

![Konfigurera sökgenvägar](./media/ConfigureShortcutsAX.png "Konfigurera sökgenvägar")

> [!NOTE]
> Om du lägger till för många genvägar kommer menyn på sökfältet i POS att bli plottrig och medarbetarens sökupplevelse kan påverkas. Vi rekommenderar att du endast lägger till så många genvägar som du behöver.

Fältet **visningsordning** anger den ordning som genvägarna visas i POS. Kriteriet som visas är de färdiga egenskaper som kundens sökalgoritm använder för att söka efter kunder. Partner kan emellertid lägga till anpassade egenskaper som sökgenvägar. Om du vill lägga till anpassade egenskaper som sökgenvägar måste systemadministratören utöka den omfattande uppräkningen (enum) som ska användas för kundsökkriterierna och markera partners anpassade egenskaper som genvägar. Partner som är ansvarig för att skriva koden för att hitta resultat när deras anpassade genvägar används i sökningar.

> [!NOTE]
> En anpassad egenskap som läggs till enum påverkar inte den standardinställda kundsökalgoritmen. Med andra ord söker inte kundens sökalgoritm i den anpassade egenskapen. Användare kan endast använda en anpassad egenskap för sökningar om den anpassade egenskapen läggs till som en genväg, eller om standardsökalgoritmen åsidosätts.

Återförsäljare kan också ställa in standardsökningsläget för kund i kassan på **Sök alla butiker**. Den här konfigurationen kan vara till hjälp i situationer där kunder som har skapats utanför kund måste sökas igenom direkt (t.ex. till och med innan fördelningsjobbet körs). För att kunna göra det måste återförsäljaren aktivera alternativet **Standardsökningsläge för kund** i funktionsprofilen för kassa. När det anges till **Ja**, varje kunds sökning gör då ett realtidssamtal till huvudkontoret.

För att förhindra att oväntade prestandaproblem döljs den här konfigurationen bakom en förhandsversionsflagga som kallas **CUSTOMERSEARCH_ENABLE_DEFAULTSEARCH_FLIGHTING**. Om du därför vill visa inställningen **standardsökläget för kunder** för kund i användargränssnittet måste återförsäljaren skapa ett acceptanstestet för användare (UAT) och produktionsmiljön. När ärendet har tagits emot arbetar teknikteamet tillsammans med återförsäljaren för att säkerställa att återförsäljaren testar i sina miljöer för icke-produktion för att bedöma prestanda och implementera eventuella optimeringar som krävs.

## <a name="cloud-powered-customer-search"></a>Molndriven kundsökning

En offentlig förhandsgranskning av kundsökningsfunktionerna med hjälp av tjänsten Azure Cognitive Search har frisläppts som en del av versionen Commerce 10.0.18. Utöver prestandaförbättringar kan tjänsteanvändare också dra nytta av en mängd förbättringar och förbättrad relevans. Prestandaförbättringar är särskilt viktiga när den globala sökfunktionen ("Sök alla butiker") i kassan används. Det beror på att sökresultaten hämtas från Azure sökindex i stället för frågor från data i Commerce-administration. 

### <a name="enable-the-cloud-powered-search-feature"></a>Aktivera den molnbaserade sökfunktionen

> [!NOTE]
> Det krävs att både Commerce-administration och Commerce Scale Unit uppdateras till version 10.0.18. Det är inte obligatoriskt att uppdatera kassa.

För att aktivera den molnstyrda sökfunktionen i Commerce-administration, följ dessa steg.

1. Gå till **Systemadministration \> Arbetsytor \> Funktionshantering**.
1. Sök efter och välj funktionen **(förhandsversion) Molndriven kundsökning** och välj sedan **Aktivera nu**.
1. Gå till **Retail och Commerce > inställning med administration > Commerce schemaläggare > Börja Commerce schemaläggare** och välj **OK** för att visa det nya jobbet **1010_CustomerSearch** i formuläret **Distributionsschema**.
1. Gå till **Butik och handel > Butik och handel-IT > Distributionsschema**.
1. Kör **1010_CustomerSearch**-jobb. Det här jobbet publicerar datumet till Azure sökindex. När indexet publiceras anges jobbets status som **Tillämpad**.
1. Efter jobbstatus **1010_CustomerSearch** anges till **Tillämpad**, kör du jobbet **1110 - Global konfiguration** för att uppdatera kassakanalerna för den nyligen aktiverade funktionen i **funktionshantering**.
1. Kör sedan jobbet **1010_CustomerSearch** regelbundet för att skicka kunduppdateringar till sökindexet.

> [!NOTE]
> För den första indexpubliceringen, jobbet **1010_CustomerSearch** kan ta några timmar att slutföra eftersom det skickar alla kundposter till Azure-sökindexet. Efterföljande uppdateringar bör ta några minuter. Under den tidsperiod då den molnbaserade sökfunktionen är aktiverad men index publiceringen ännu inte slutförts, kommer kundsökningen från kassan att standardvärdet visas som standard i den befintliga SQL-baserade sökningen. På så sätt ser du till att det inte blir fel med butiksoperationer.

### <a name="functional-differences-from-the-existing-search"></a>Funktionella differenser från den befintliga sökningen

Följande lista visar hur den molnbaserade kundsökningsfunktionen skiljer sig från den befintliga sökfunktionen. 

- Kunder som skapas och redigeras i Commerce-administraion skickas till Azure-sökindexet **1010_CustomerSearch** jobbet körs. Dessa uppdateringar tar minst 15 till 20 minuter att uppdatera index. Kassaanvändare kan söka efter nya kunder (eller söka efter uppdaterad information) ungefär 15 till 20 minuter efter att uppdateringarna har inträffat i Commerce-administration. Om din affärsprocess kräver att kunder som har skapats i Commerce-administration är omedelbart sökbara i kassan, kanske detta inte är rätt tjänst åt dig.
- Nya kunder som skapas i kassan skickas till Azure-sökindexet från Commerce Scale Unit och kan omedelbart sökas i valfri butik. Men om funktionen för skapande av asynkrona kunder är aktiverad kommer nya kundposter inte att publiceras i Azure-sökindex från Commerce Scale Unit och kommer inte att kunna sökas från kassa förrän kundinformationen synkroniseras med Commerce-administration och kund-ID skapas för asynkrona kunder. Jobbet **1010_CustomerSearch** kan sedan skicka asynkrona kundposterna till Azure-sökindexet. I genomsnitt kommer det att vara ungefär 30 minuter innan nya asynkrona kunder kan sökas i kassa. I uppskattningen förutsätts det att **1010_CustomerSearch**, **P-jobb** och jobbet **Synkronisera kunder och affärspartners från asynkront läge** är planerade att köras var 15:e minut.
- Molnbaserad sökning söker också efter sekundära e-postmeddelanden och telefonnummer till kunder, men för närvarande visar kundsökresultaten bara kundernas primära telefonnummer och primära e-postadress. Vid en första ansökning kan det se ut som om irrelevanta sökresultat har returnerats, men om du kontrollerar den sekundära e-postadressen och det sekundära telefonnumret för en kund i sökresultaten kan det hjälpa till att kontrollera om det eftersökta nyckelordet resulterade i en kundmatch. För att undvika sådan förvirring finns det planer på att förbättra sökresultatsidan för att göra det enkelt för användarna att förstå varför ett sökresultat returnerades.
- Kravet på att söka med minst fyra tecken i en global sökning ("Sök alla butiker") kan inte tillämpas på denna tjänst.

> [!NOTE]
> Sökfunktionen för kunder med hjälp av tjänsten Azure Cognitive Search finns tillgänglig i begränsade regioner för förhandsgranskning. Sökfunktionen för kunder är *inte* tillgänglig i följande regioner:
> - Brasilien
> - Indien
> - Kanada
> - Storbritannien

[!INCLUDE[footer-include](../includes/footer-banner.md)]
