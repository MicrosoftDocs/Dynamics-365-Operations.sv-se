---
title: Ställ in validering av Fakturamatchning för leverantörsreskontra
description: Det här avsnittet innehåller information om hur du ställer in validering av Fakturamatchning för leverantörsreskontra.
author: abruer
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 15fbb5481e3ff8760f536f1d5eeff76370216b37
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827756"
---
# <a name="set-up-accounts-payable-invoice-matching-validation"></a>Ställ in validering av Fakturamatchning för leverantörsreskontra

[!include [banner](../../includes/banner.md)]

Innan du börjar kontrollerar du att konfigurationsnyckeln för fakturamatchning har valts. Om din juridiska person spårar utgifter, till exempel frakt, genom att använda avgifter, se till att Konfigurationsnycklar för Tillägg har valts.  Fakturamatchning i leverantörsreskontra är den process där information om leverantörsfaktura, inköpsorder och produktinleverans matchas. Skillnader mellan dessa dokument kallas för matchningsavvikelser. Matchningsavvikelser jämförs med toleranserna som ställts in. Om en matchningsavvikelse överskrider toleransprocenten eller toleransmängden visas matchningsavvikelseikoner på sidan **Leverantörsfaktura** och på sidan **Fakturamatchningsuppgifter**.

## <a name="determine-which-invoice-matching-validation-to-use"></a>Ange vilken validering av fakturamatchning som ska användas
Fyra olika typer av matchningsvalideringar är tillgängliga. 

- **Radnivåmatchning** – den vanligaste typen av matchning är radmatchning. Radnivåmatchning kan vara tvåvägs- och trevägsradsmatchningspolicy. Standardinställda ranivåmatchningen kan anges för en juridisk person på sidan **parameter för leverantörsreskontra**. Tvåvägsmatchning jämför enhetspriset på fakturan med enhetspriset på inköpsordern. Vid trevägsmatchning jämförs fakturakvantitet också med den matchade kvantiteten för produktinleverans.
- **Matchning av fakturasummor** – Matcha de totala beloppen på fakturan med de totala beloppen på inköpsordern. Den här typen av fakturamatchning inkluderar minst mängd information, så du kan använda det här alternativet för att ställa in kontroller som minimerar personaltiden som behövs för att granska information om fakturamatchning. Sex summor jämförs, inklusive delsumma, total rabatt, avgifter, moms, avrundning och fakturabelopp. Systemet validerar om något av dessa värden på fakturan avviker från förväntade belopp med mer än en acceptabel avvikelse.
- **Avgiftsmatchning** – Matcha avgiftsinformation (belopp) på fakturan med avgiftsinformation (belopp) på inköpsordern.
- **Prissummor för radartikelmatchning** – den här typen av matchning är användbar för företag som vanligtvis tar emot flera fakturor för en enda inköpsorderrad. Om du normalt bara tar emot en faktura per inköpsorderrad är den här typen av matchning inte nödvändig. Denna matchning kräver att tvåvägs eller tredimensionell matchning är aktiverad och fungerar som en nettobeloppsvalidering som inte får överskridas baserat på toleransprocent och toleransbelopp.  Denna typ av matchning jämför prisinformation för nettobeloppet för varje rad på fakturan, och alla väntande och tidigare bokförda fakturarader, med nettobeloppet för den motsvarande inköpsorderraden. Nettobeloppet beräknas med följande formel: (Enhetspris * Radkvantitet) + Radavgifter – Radrabatter När du matchar prissummor efter procent jämför systemet värden i transaktionsvalutan. När du matchar prissummor efter belopp jämför systemet värden med redovisningsvalutan.

## <a name="set-up-parameters-to-enable-invoice-matching-validation"></a>Konfigurera parametrar för validering av fakturamatchning
1. Gå till **Leverantörsreskontra > Inställningar > Parametrar för leverantörsreskontra.**
2. Välj fliken **Fakturavalidering**
3. Markera eller avmarkera kryssrutan **Aktivera fakturamatchningsvalidering**.
    * Välj om godkännande ska krävas innan du bokför en faktura som innehåller fakturamatchningsavvikelser. Om det anges om du vill **tillåta med varning**, kommer den visuella indikationen på se när avvikelser för fakturamatchning överskrider toleransen. Om du att kunna i stånd till att bokföra fakturan. För att använda arbetsflöden tillsammans med validering av fakturamattchning ska du se till att **Bokför faktura med avvikelser** anges till **tillåta med varning** för att undvika godkänna flera gånger.  
    * I fältet **Uppdatera status för fakturahuvud automatiskt** välj om matchning ska utföras automatiskt under fakturainmatning av systemet. Rekommenderat ange är **Ja**, om du inte datapostprestandabekymmer upplever. När du avaktiverar automatiska uppdateringar kan aktivera snabbare, eftersom systemets prestanda fakturamatchningvalideringen ska kopplas efter vid inmatning. Datapostkontoristen måste uppdatera manuellt fakturans matchstatusen för att se fakturamatchningvalideringresultaten, när den inte anges till **Nej**.  
4. Ställ in **Matchning av fakturasummor**.
5. Markera eller avmarkera kryssrutan **Matchning av fakturasummor** för att matcha verkliga fakturasummor med förväntade summor.
    * Välj om en ikon ska visas om avvikelser för fakturamatchning överskrider toleransen. Du kan välja att visa ikonen när en positiv diskrepans överskrider toleransen, eller när antingen en positiv eller negativ diskrepans överskrider toleransen.  
    * Toleransen är till exempel 5 procent och det totala fakturabeloppet på inköpsordern är 100,00. Därför visas en prismatchningsikon om det totala fakturabeloppet på fakturan överstiger 105.00. Om du väljer **Om större eller mindre än tolerans**, visas också en ikon om fakturabeloppet är mindre än 95,00.  
6. I fältet **Toleransprocent för fakturasummor** anger du den procentuella avvikelse som är acceptabel. Det här värdet är standardvärdet för företaget. Detta värde kan åsidosättas för specifika leverantörer med hjälp av sidan **Toleranser för fakturasummor**. Information om hur du åsidosätter toleransprocenten för fakturasummor för en viss leverantör finns i avsnittet "ställa in matchningstolerans för fakturasummor för leverantörer" senare i det här avsnittet.
7. Ange **Pris- och kvantitetsmatchning**.
8. Välj ett värde som ska användas som standardpolicy för den juridiska person som du arbetar med i fältet **Radmatchningspolicy**. **Krävs ej** innebär att det inte finns någon verifiering av enskilda fakturaradspriser till inköpsorderpris- eller fakturakvantiteter till obligatoriska följesedelns kvantiteter. **Tvåvägsmatchning** betyder att verifieringen med fakturarader krävs men endast inköpsordern och leverantörens fakturadokumenten ingår i verifieringen. Produktinleveransen faktorer inte till de matcha de valideringar. **Trevägsmatchning** betyder att fakturans nettoenhetspris ska jämföras med inköpsorderns netto enhetspris och matcha den produktinleveranskvantiteten ska jämföras med kvantiteten.
9. Om du vill tillåta en annan matchningsnivå för en artikel, leverantör, leverantör och artikel i kombination eller en inköpsorderrad, väljer du ett värde i fältet **Tillåt åsidosättning av matchningspolicy**. Radmatchningspolicyn för den juridiska personen kan åsidosättas för en specifik leverantör, artikel eller kombination av leverantör och artikel på sidan **matchningspolicy**.
    * Om du använder en rad matchningspolicy av tvåvägs matcha eller trevägsmatcha, kan du ange procentsatser för pristoleranser för dina juridisk person, artiklar och leverantörer på sidan för **artikelpristolerans**. Den juridiska personens standardpristolerans sätts till noll procent för tvåvägs- och trevägsmatchning. När leverantörsfakturor jämförs med informationen i inköpsorder görs en sökning efter tillämpliga toleransprocentsatser.   
10. Välj ett värde i fältet **Matcha prissummor** för att matcha prissummor för radartiklar på fakturor. Den här typen av att de är praktiskt, när leverantören skickar flera fakturor för samma inköpsorderraden. Du kan jämföra prisinformation för nettobeloppet för varje rad på fakturan, och alla väntande och tidigare bokförda fakturarader, med nettobeloppet för den motsvarande inköpsorderraden.  Alternativen är **ingen**, **procent**, **belopp** eller **procent och belopp**.
11. I fältet **Toleransprocent för inköpsprissumma** anger du en procentsats av den avvikelse som du godtar. Det här fältet är bara tillgängligt om **Matcha prissummor** anges **Procentandel** eller **Procentandel och belopp**.
12. I fältet **Tolerans för inköpsprissumma**, ange ett belopp i redovisningsvalutan. Det här fältet är bara tillgängligt om **Matcha prissummor** anges **Belopp** eller **Procentandel och belopp**.
13. I fältet **Visa matchningsikon för prissumma**, välj om en ikon visas, om avvikelser för fakturamatchning överskrider toleransen för nettopriset per enhet i fältet . Ikonen kan visas när en positiv diskrepans överskrider toleransen, eller när antingen en positiv eller negativ diskrepans överskrider toleransen.
Toleransen är till exempel 5 procent och radprissumman på inköpsordern är 10,00. Därför visas en prismatchningsikon om summan på fakturans prisrad överstiger 10.50. Om du väljer **Om större eller mindre än tolerans**, visas också en ikon om det totala radprist på fakturan är mindre än 9,50.
13. Ange avgiftsmatchning
14. Markera kryssrutan **Matcha avgifter** om du vill matcha verkliga transaktioner mot förväntade kostnader.

## <a name="set-up-unit-price-tolerance-percentages"></a>Ställ in toleransprocentsatser för enhet
Gå till **Leverantörsreskontra > Inställningar > Fakturamatchningsinställning > Pristoleranser** för att definiera tillåtna procentsatser för pristoleranser. Om du använder en rad matchningspolicy av tvåvägs matcha eller trevägsmatcha, kan du ange procentsatser för pristoleranser för dina juridisk person, artiklar och leverantörer. När leverantörsfakturor jämförs med informationen i inköpsorder görs en sökning efter tillämpliga toleransprocentsatser. Följande är standardsökordning:
* Register/tabell
* Register/grupp
* Register/alla
* Grupp/register
* Grupp/grupp
* Grupp/alla
* Alla/register
* Alla/grupp
* Alla/alla

Standardpristoleransen för den juridiska personen är 0 procent, och denna pristolerans tillämpas på alla artiklar och alla konton (Alla, Alla). Du kan inte ta bort posten för den juridiska personens standardpristolerans.

Som standard tillåts negativa prisavvikelser. Du kan dock inte ange ett negativt tal som pristoleransprocentsats. Om du vill spåra negativa toleransprocent för pris väljer du **Om större eller mindre än tolerans** i fältet **Visa matchningsikonen för enhetspris** på sidan **Parametrar för leverantörsreskontra**. Ange sedan procentsatser för pristoleranser på sidan **pristoleranser**.

## <a name="set-up-matching-policy-override"></a>Ange åsidosättning av matchningspolicy

Gå till **Leverantörsreskontra > Inställningar > Fakturamatchningsinställningar > matchningspolicy** för att definiera standardvärdet för fältet matchningspolicy för rader i inköpsorderformuläret. Detta är en valfri inställning. Använd det här formuläret om du vill ställa in en dubbelriktad matchning eller en tresiffrig matchning för artiklar, leverantörer eller artikel- och leverantörskombinationer. Med dessa poster kan du definiera mer detaljerade matchningsprinciper än vad som matchar den juridiska enhetsmatchningspolicyn som du har definierat på sidan **parametrar för leverantörsreskontra**. Standardinställda matchningspolicyn för en juridisk person gäller för alla artiklar och leverantörer förutom de för vilka en annan radmatchningspolicy har angetts på den här sidan.

På denna sida välj **Matchningspolicynivå**. Välj nivå i matchningspolicyhierarkin för att ställa in radmatchningspolicyer för.

- **Artikel och leverantör** – ange matchningspolicy för specifika artiklar som köps från vissa leverantörer.
- **Artikel** – ange matchningspolicyn för specifika artiklar som köps från en leverantör, förutom de som anges på artikel- och leverantörsnivå.
- **Leverantör** – ange matchningspolicyn för alla artiklar som köps från specifika leverantörer, förutom de som anges på artikel- och artikel- och leverantörsnivå.
  
Följande hierarki används för att bestämma matchningspolicyn som används:
  *  Artikel och leverantör
  *  Objekt
  *  Leverantör
  *  Juridisk person
  
## <a name="set-up-invoice-totals-matching-tolerance-for-vendors"></a>Ställ in fakturasummor som matchar toleransen a för leverantörer

Gå till **Leverantörsreskontra > Inställningar > Fakturamatchningsinställningar > Toleranser för fakturasummor** för att ange leverantörsspecifika toleranser för matchande fakturasummor. Matchningsberäkningen använder toleransprocentsatser för fakturasummor från det leverantörskonto som anges som orderkonto på leverantörsfakturan. Om leverantörskontot inte har en angiven toleransprocentsats för fakturasummor används den toleransprocentsats för fakturasummor som har angetts för den juridiska personen på sidan **parameter för leverantörsreskontra**.

1. För att ange toleranserna för enskilda leverantörer som åsidosätter standardtoleransen, välj ett **Leverantörskonto**.
2. Ange avvikelseprocent som du accepterar för den här leverantör.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]