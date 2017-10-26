---
title: "Produktsökning och kundsökning i kassa"
description: "Det här avsnittet innehåller en översikt över de förbättringar som har gjorts i produkt- och kundsökfunktionen i Dynamics 365 for Retail."
author: shalabhjain
manager: AnnBe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.search.scope: Operations, Retail
ms.custom: 141393
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 66859535ee118ffc04a847dfe6e8e0bae1cd9d6c
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="overview-of-product-and-customer-search-in-point-of-sale"></a>Översikt över produkt- och kundsök i kassan

Modern kassa (Modern Point Of Sale, eller MOPS) samt molnbaserad kassa (Cloud Point Of Sale, eller CPOS) ger en lättanvänd sökfunktion som gör det möjligt för butikspersonal att snabbt söka efter produkter och kunder. Sökfältet finns alltid överst i MOPS och CPOS, så att personalen snabbt kan hitta produkter och kunder.

Personalen kan söka efter produkter i det sortiment och de kataloger som hör till den aktuella butiken, samt i sortiment och kataloger som hör till andra butiker i företaget. Därför kan kassörerna sälja och returnera produkter utanför butikens sortiment. Medarbetare kan dessutom söka efter kunder som är associerade med den aktuella butiken eller andra butiker i företaget. Medarbetare kan dessutom söka efter kunder som är kopplade till ett annat företag i moderorganisationen.

## <a name="product-search"></a>Produktsökning 

Som standard utförs en produktsökning på butikssortimentet. Denna typ av sökning kallas en *lokal produktsökning*. Medarbetare kan emellertid enkelt växla till valfri katalog som är kopplad till den aktuella butiken, eller också söka i en annan butik. Denna typ av sökning kallas en *fjärrproduktsökning*. Välj knappen **Kategorier** till vänster på sidan för att byta katalog. Överst i fönstret som visas väljer du knappen **Ändra katalog** och väljer sedan en av de tillgängliga katalogerna för att titta på den. Systemet söker den valda katalogen för produkter.

På sidan **Ändra katalog** kan personalen enkelt välja valfri butik, eller också kan de söka efter produkter i alla butiker.

![Ändra katalog](./media/Changecatalog.png "Ändra katalog")
 
En lokal produktsökning söker inom följande produktegenskaper:

- Produktnummer
- Produktnamn
- beskrivning
- Dimensioner
- Streckkod
- Söknamn

### <a name="enhancements-to-local-product-searches"></a>Förbättringar av lokala produktsökningar

Upplevelsen av lokala produktsökningar har gjorts mer användarvänlig. Följande förbättringar har också gjorts:

- Listrutemenyer för produkter och kunder har lagts till i sökfältet så att medarbetare kan välja antingen **Produkt** eller **Kund** innan de genomför sökningen. Som standard har **Produkt** markerats, vilket visas i bilden nedan.
- För flera nyckelordssökningar (det vill säga, för sökningar med sökvillkor) kan återförsäljare ange om sökresultatet ska innehåll resultat som matchar alla sökord eller endast resultat som matchar alla sökord. Den här inställningen finns i kassans funktionalitetsprofil under en ny grupp som heter **Produktsökning**. Standardinställningen är **Matcha alla sökord**. Detta är också den rekommenderade inställningen. När inställningen **Matcha alla sökord** används kommer alla produkter som helt eller delvis matchar ett eller flera sökord att returneras, och resultatet sorteras automatiskt i stigande ordning efter de produkter som har flest nyckelordsträffar (helt eller delvis).

    Inställningen **Matcha alla sökvillkor** returnerar endast produkter som matchar alla söktermer (helt eller delvis). Denna inställning är praktisk när produktnamnen är långa och medarbetarna endast vill visa begränsade produkter i sökresultaten. Denna typ av sökning har emellertid två begränsningar:

    - Sökningen utförs på individuella produktegenskaper. Exempelvis returneras bara produkter som har de sökta nyckelorden i minst en produktegenskap.
    - Dimensioner genomsöks inte.

- Återförsäljare kan nu konfigurera produktsökningen så att denna visar sökförslag när användarna skriver produktnamn. En ny inställning för denna funktion finns i kassafunktionens profil, under en grupp som heter **Produktsökning**. Inställningen kallas **Visa sökförslag medan du skriver**. Denna funktion hjälper anställda att snabbt hitta den produkt som de söker efter, detta eftersom de inte behöver skriva hela namnet manuellt.
- Sökalgoritmen för produkten söker nu också efter de sökta villkoren i produktens **Söknamn**-egenskap.

![Produktförslag](./media/Productsuggestions.png "Produktförslag")

## <a name="customer-search"></a>Sök efter kund

Kundsök används för att hitta kunder för olika ändamål. Kassörer kan exempelvis visa en kunds önskelista eller inköpshistorik, eller lägga till kunden i en transaktion. När det gäller sökningar med flera nyckelord returnerar kundsökningens algoritm alla kunder som matchar något av de nyckelorden som sökts. De kunder som matchar de flesta nyckelorden visas emellertid överst i resultatet. Detta motsvarar hur andra sökmotorer visar sina resultat. De visar först de resultat som matchar flest söktermer. Därefter visas de resultat om delvis matchar sökningens nyckelord. Detta gör det enklare för kassörerna i situationer där de använder flera nyckelord för sin sökning, men ett av nyckelorden är felstavat.

En kundsökning utförs som standard på kund-adressböcker kopplade till butiken. Denna typ av sökning kallas en *lokal kundsökning*. Medarbetare kan emellertid också söka efter kunder globalt. Med andra ord kan man söka i samtliga företagets butiker och mellan alla juridiska personer. Denna typ av sökning kallas en *fjärrkundsökning*.

För att genomföra en global sökning kan personalen använda knappen **Filtrera resultat** längst ned på sidan och sedan alternativet **Sök alla butiker** som visas på bilden nedan. I detta fall returneras inte bara kunder. Alla typer av parter som ingår i en adressbok på huvudkontoret returneras också. Dessa parter inkluderar medarbetare, leverantörer, kontakter och konkurrenter.

> [!NOTE]
> Minst fyra tecken måste anges för en fjärrkundsökning för att denna ska returnera resultat.

I samband med fjärrkundsökning visas inte kundens ID för kunder från andra juridiska personer, detta eftersom inget kund-ID har skapats för dessa parter i det aktuella företaget. Om en medarbetare emellertid öppnar sidan för information om kunden kan systemet automatiskt generera ett kund-ID för parten, och kopplar också ihop butikens kundadressböcker med kunden. Därför syns kunden i lokala butikssökningar som utförs senare.

![Global kundsökning](./media/Globalcustomersearch.png "Global kundsökning")

### <a name="enhancements-to-local-customer-searches"></a>Förbättringar av lokala kundsökningar

Lokala kundsökningar hjälper anställda att snabbt hitta kunder efter telefonnummer. Medarbetarna slipper skriva in specialtecken som har lagts till i en kunds telefonnumret, t.ex. blanksteg, bindestreck och parenteser. Även om kassörer kan lagra telefonnummer i valfritt format (till exempel kan de innehålla hakparenteser, bindestreck, symboler och så vidare) kan de kan söka efter kunder genom att delvis skriva in ett telefonnummer. Om en kassör inkluderar specialtecken när han eller hon anger ett telefonnummer, kan andra kassörer hitta kunden genom att skriva in de siffror som visas efter specialtecknen. Om ett kundtelefonnummer exempelvis angetts som **123-456-7890** kan en kassör söka efter kunden genom att skriva in **123**, **456**, **7890** eller **1234567890**, eller genom att delvis ange de första siffrorna i telefonnumret.

