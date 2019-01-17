---
title: "Produkt- och kundsökning i kassan (POS)"
description: "Det här avsnittet innehåller en översikt över de förbättringar som har gjorts i produkt- och kundsökfunktionen i Microsoft Dynamics 365 for Retail."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 03/28/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 50b0cec27e343b3b6aba464a04c9883160ab263a
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---

# <a name="product-search-and-customer-search-in-the-point-of-sale-pos"></a>Produkt- och kundsökning i kassan (POS)

[!include [banner](includes/banner.md)]

Modern kassa (Modern Point Of Sale, eller MOPS) samt molnbaserad kassa (Cloud Point Of Sale, eller CPOS) ger en lättanvänd sökfunktion för att snabbt söka efter produkter och kunder. Eftersom sökfältet alltid finns överst i fönstrena MOPS och CPOS kan personalen snabbt söka produkter och kunder.

Medarbetare kan söka efter produkter i sortimentet och kataloger som hör till den aktuella butiken. De kan också söka efter produkter i sortimentet och kataloger som hör till alla andra butiker i företaget. Därför kan kassörerna sälja och returnera produkter utanför butikens sortiment. Medarbetare kan dessutom söka efter kunder som är associerade med den aktuella butiken eller andra butiker i företaget. Medarbetare kan dessutom söka efter kunder som är kopplade till ett annat företag i moderorganisationen.

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

Upplevelsen av lokala produktsökningar har nu gjorts mer användarvänlig. Följande förbättringar har också gjorts:

- Listrutemenyer för produkter och kunder har lagts till i sökfältet så att medarbetare kan välja antingen **Produkt** eller **Kund** innan de genomför sökningen. Som standard har **Produkt** markerats, vilket visas i bilden nedan.
- För flera nyckelordssökningar (det vill säga, för sökningar med sökvillkor) kan återförsäljare ange om sökresultatet ska innehåll resultat som matchar *alla* sökord eller endast resultat som matchar *alla* sökord. Den här inställningen finns i kassans funktionalitetsprofil i en ny grupp som heter **Produktsökning**. Standardinställningen är **Matcha alla sökord**. Detta är också den rekommenderade inställningen. När inställningen **Matcha alla sökord** används returneras alla produkter som helt eller delvis matchar ett eller flera sökord som resultat. Resultaten sorteras automatiskt i stigande ordning efter produkter som har de flesta nyckelordsträffarna (helt eller delvis).

    Inställningen **Matcha alla sökvillkor** returnerar endast produkter som matchar alla söktermer (helt eller delvis). Denna inställning är praktisk när produktnamnen är långa och medarbetarna endast vill visa begränsade produkter i sökresultaten. Denna typ av sökning har emellertid två begränsningar:

    - Sökningen utförs på individuella produktegenskaper. Exempelvis returneras bara produkter som har de sökta nyckelorden i minst en produktegenskap.
    - Dimensioner genomsöks inte.

- Återförsäljare kan nu konfigurera produktsökningen så att denna visar sökförslag när användarna skriver produktnamn. En ny inställning för denna funktion finns i kassafunktionens profil, i en grupp som heter **Produktsökning**. Inställningen kallas **Visa sökförslag medan du skriver**. Denna funktion hjälper anställda att snabbt hitta den produkt som de söker efter, detta eftersom de inte behöver skriva hela namnet manuellt.
- Sökalgoritmen för produkten söker nu också efter de sökta villkoren i produktens **Söknamn**-egenskap.

    ![Produktförslag](./media/Productsuggestions.png "Produktförslag")

## <a name="customer-search"></a>Sök efter kund

Kundsök används för att hitta kunder för olika ändamål. Kassörer kan exempelvis visa en kunds önskelista eller inköpshistorik, eller lägga till kunden i en transaktion. När det gäller sökningar med flera nyckelord returnerar kundsökningens algoritm alla kunder som matchar något av de nyckelorden som sökts. De kunder som matchar de flesta nyckelorden visas emellertid överst i resultatet. Detta motsvarar hur andra sökmotorer visar sina resultat. De visar först de resultat som matchar flest söktermer. Därefter visas de resultat om delvis matchar sökningens nyckelord. Detta gör det enklare för kassörerna i situationer där de använder flera nyckelord för sin sökning, men ett av nyckelorden är felstavat.

En kundsökning utförs som standard på kund-adressböcker kopplade till butiken. Denna typ av sökning kallas en *lokal kundsökning*. Medarbetare kan emellertid också söka efter kunder globalt. Med andra ord kan man söka i samtliga företagets butiker och mellan alla juridiska personer. Denna typ av sökning kallas en *fjärrkundsökning*.

För att genomföra en global sökning kan personalen använda knappen **Filtrera resultat** längst ned på sidan och sedan alternativet **Sök alla butiker** som visas på bilden nedan. I detta fall returneras inte bara kunder. Alla typer av parter som ingår i en adressbok på huvudkontoret returneras också. Dessa parter inkluderar medarbetare, leverantörer, kontakter och konkurrenter.

> [!NOTE]
> Minst fyra tecken måste anges för en fjärrkundsökning för att denna ska returnera resultat.

I samband med fjärrkundsökning visas inte kundens ID för kunder från andra juridiska personer, detta eftersom inget kund-ID har skapats för dessa parter i det aktuella företaget. Om en medarbetare emellertid öppnar sidan för information om kunden kan systemet automatiskt skapa ett kund-ID för parten, och kopplar också ihop butikens kundadressböcker med kunden. Därför syns kunden i lokala butikssökningar som utförs senare.

![Global kundsökning](./media/Globalcustomersearch.png "Global kundsökning")

### <a name="enhancements-to-local-customer-search"></a>Förbättringar av lokala kundsökningar

Sökningar som är baserade på telefonnummer har förenklats. Dessa sökningar kan nu ignorera specialtecken såsom blanksteg, bindestreck och parenteser som kan ha lagts till när kunden skapades. Därför behöver kassörerna inte ta hänsyn till telefonnummerformatet när de söker. De kan även söka efter kunder genom att skriva en del av ett telefonnummer. Om ett telefonnummer innehåller specialtecken kan du även hitta det genom att söka efter de siffror som visas efter specialtecknet. Om ett kundtelefonnummer exempelvis angetts som **123-456-7890** kan en kassör söka efter kunden genom att skriva in **123**, **456**, **7890** eller **1234567890**, eller genom att ange de första siffrorna i telefonnumret.

Vanlig kundsökning kan vara tidskrävande, eftersom den söker över flera fält. Kassörer kan istället nu söka i en anpassad egenskap, till exempel namn, telefonnummer eller e-postadress. Egenskaper som kundens sökalgoritm använder kallas *sökvillkor för kund*. Systemadministratören kan enkelt konfigurera ett eller flera kriterier som genvägar som visas i kassan. Eftersom sökningen är begränsat till ett enda villkor visas endast relevanta sökresultat och den får mycket bättre prestanda än en standardkundsökningsprestanda. I följande illustration visas kundens sökgenvägar i kassan.

![Kundens sökgenvägar](./media/SearchShortcutsPOS.png "Kundens sökgenvägar")

Om du vill ange sökvillkor som genvägar måste administratören öppna sidan **Butiksparametrar** i Microsoft Dynamics 365 for Finance and Operations och sedan på fliken **Sökvillkor för kassa** väljer du de kriterier som ska visas som genvägar.

![Konfigurera sökgenvägar](./media/ConfigureShortcutsAX.png "Konfigurera sökgenvägar")

> [!NOTE]
> Om du lägger till för många genvägar kommer menyn på sökfältet i kassan att bli plottrig och medarbetarens sökupplevelse kan påverkas. Vi rekommenderar att du endast lägger till så många genvägar som du behöver.

Fältet **visningsordning** anger den ordning som genvägarna visas i kassan. Kriteriet som visas är de färdiga egenskaper som kundens sökalgoritm använder för att söka efter kunder. Partner kan emellertid lägga till anpassade egenskaper som sökgenvägar. Om du vill lägga till anpassade egenskaper som sökgenvägar måste systemadministratören utöka den omfattande uppräkningen (enum) som ska användas för kundsökkriterierna och markera partners anpassade egenskaper som genvägar. Partner som är ansvarig för att skriva koden för att hitta resultat när deras anpassade genvägar används i sökningar.

> [!NOTE]
> En anpassad egenskap som läggs till enum påverkar inte den standardinställda kundsökalgoritmen. Med andra ord söker inte kundens sökalgoritm i den anpassade egenskapen. Användare kan endast använda en anpassad egenskap för sökningar om den anpassade egenskapen läggs till som en genväg, eller om standardsökalgoritmen åsidosätts.

