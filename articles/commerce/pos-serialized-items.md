---
title: Arbeta med serialiserade artiklar i kassa
description: I det här avsnittet beskrivs hur du hanterar serialiserade artiklar i programmet kassa (POS).
author: boycezhu
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 39135111a8e7bf16d1e56ca42726ae8a8e130c5d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798691"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Arbeta med serialiserade artiklar i kassa

[!include [banner](includes/banner.md)]

Många återförsäljare säljer produkter som kräver seriell kontroll. Dessa produkter kallas för *serialiserade artiklar*. En del återförsäljare kanske vill behålla serienummer i butik eller på lagerplats för spårning. Andra återförsäljare kan vilja samla serienummer under försäljningsprocessen, för service- och garantisyften. I det här avsnittet beskrivs hur du kan hantera serialiserade artiklar i programmet Microsoft Dynamics 365 Commerce kassa (POS).

## <a name="serial-number-configurations"></a>Konfiguration av serienummer

En artikel betraktas som en serialiserad artikel om den tilldelas en spårningsdimensionsgrupp som tillåter serienummer. I Commerce-administration på sidan **spårningsdimensionsgrupper** välj alternativet **aktiv** för att aktivera serienummer för lagerprocessen, eller välj alternativet **aktiv i försäljningsprocess** för att aktivera serienummer för försäljningsprocessen.

På snabbfliken **Spårningsdimensioner** aktivera parametern **Tom inleverans tillåten** för att tillåta serienumret vara valfri indata under lagerinleveransen. Om du inaktiverar den här parametern tvingas serienummer att vara en obligatorisk inmatning. På samma sätt kontrollerar parametern **Tom utleverans tillåten** om serienummer krävs under lagerförsändningsprocess.

> [!NOTE]
> För att använda kassaåtgärderna **Inkommande lager** och **Utgående lager** för att registrera eller verifiera en serialiserad artikel, måste artikeln tilldelas en spårningsdimensionsgrupp som är inställd på att tillåta serienummer för alternativet **Aktiv** eller alternativet **Aktiv i försäljningsprocess**.

## <a name="serial-number-management-page"></a>Sidan för hantering av serienummer

I kassaåtgärderna **Inkommande lager** och **Utgående lageråtgärder** om artikeln som väljs, tas emot eller skickas är en serieartikel innehåller **Detaljer** innehåller ett alternativ för **Hantera serienummer** som länkar till sidan **hantering av serienummer** där du kan registrera eller validera artikelns serienummer. Alternativt kan du öppna sidan **Hantering av serienummer** genom att välja åtgärd **Serienummer** i programfältet i vyn för orderspecifikationer eller genom att välja **Hantera serienummer** i dialogrutan som visas vid inleveransen. 

På sidan **Hantering av serienummer** visas alla öppna serienummerrader som väntar på registrering eller verifiering. Det kan finnas två flikar på den här sidan: en för den aktuella artikeln och en för alla serialiserade artiklar på ordern.

I fältet **Status** på sidan **Hantering av serienummer** finns information om den aktuella fas som varje serienummer är i:

- **Ej registrerat** – Serienumret har inte angetts eller så har det förregistrerade serienumret inte verifierat än (i inleveransprocessen).
- **Registrerar** – Serienumret har registrerats och sparats lokalt i butikens kanaldatabas, eller så har det förregistrerade serienumret verifierats. Endast serienummer med status **Registrerar** skickas till Commerce-administration när du har tagit emot det eller uppfyllelse.

## <a name="receive-serialized-items"></a>Inleverera serialiserade artiklar

Med åtgärden **Inkommande lager** i kassaåtgärden kan användare utföra följande uppgifter för serialiserade artiklar:

- Registrera serienummer mot serialiserade artiklar när artiklarna tas emot i butiken via en inköpsorder.
- Verifiera förregistrerade serienummer mot serialiserade artiklar när artiklarna tas emot i butiken via en inköps- eller överföringsorder.

### <a name="register-serial-numbers-against-serialized-items"></a>Registrera serienummer mot serialiserade artiklar

För en inköpsorder kommer du att uppmanas med en dialogruta med alternativet **Hantera serienummer** under mottagningsprocessen för en serieartikel. Du kan välja att öppna sidan **Hantering av serienummer** och börja registrera serienummer. Du kan också hoppa över det här steget under inleveransen och ange indata senare innan inleveransen bokförs.

Som standard visas fliken för den aktuella artikeln. Alla serienummerrader har ett tomt serienummervärde och status **Inte registrerat**. Du kan skanna serienummerstreckkoder, eller välja **Serienummer** i appfältet för att kontinuerligt ange serienummer. Serienumren som du anger visas i listan och deras status ändras till **Registrerar**. Maximalt antal serienummer som du kan registrera i listan är lika med inleveranskvantiteten. Om du gör fel kan du välja **Redigera** eller **Rensa** i fältet **Detaljer** för att ändra serienummer du har angett.

Du kan även registrera serienummer på fliken **Alla serialiserade artiklar** på sidan för **Hantering av serienummer**. I listan väljer du den artikel du vill registrera serienummer mot.

### <a name="validate-serial-numbers-on-serialized-items"></a>Verifiera serienummer för serialiserade artiklar

För en överföringsorder måste den utgående sidan förregistrera serienummer på de serialiserade artiklarna under leveransprocessen. För en inköpsorder kan leverantören tillhandahålla information om serienummer via leveransavisering (ASN) och du kan sedan förregistrera nummer för de artiklar som ska levereras. I båda fallen är serienumren kända före inleveransen. På inkommande sidan måste du därför bara verifiera att du har fått det du skulle ha.

Om du vill validera serienummer kan du öppna sidan **Hantering av serienummer**, antingen under inleveransen eller när som helst innan inleveransen bokförs. För alla serialiserade artiklar som har förregistrerade serienummer, ställs alla serienummer automatiskt in med ursprunglig status som **Inte registrerad** på den här sidan. Om du vill verifiera serienummer kan du skanna in eller ange dem. När serienummer anges verifierar programmet om de matchar förregistrerade serienummer. Om de matchar ändras deras status till **Registrerar**. Annars får du ett felmeddelande. Alternativt kan du välja ett serienummer direkt och sedan välja alternativet **Validera serienummer** i fönstret **Detaljer** för att snabbt markera serienumret som validerat. Maximalt antal serienummer som du kan verifiera i listan är lika med inleveranskvantiteten

Du kan även verifiera serienummer på fliken **Alla serialiserade artiklar** på sidan för **Hantering av serienummer**. I listan väljer du den artikel du vill verifiera serienummer mot.

## <a name="ship-serialized-items"></a>Leverera serialiserade artiklar

Du kan använda den **Utgående lageråtgärder** kassaåtgärden för att registrera serienummer mot serialiserade artiklar när de levereras ut ur den aktuella butiken via en överföringsorder.

### <a name="register-serial-numbers-against-serialized-items"></a>Registrera serienummer mot serialiserade artiklar

För en överför kommer du att uppmanas med en dialogruta med alternativet **Hantera serienummer** under leveransprocess för en serieartikel. Du kan välja att öppna sidan **Hantering av serienummer** och börja registrera serienummer. Du kan också hoppa över det här steget under leveransprocess och ange indata senare innan leverans bokförs.

Som standard visas fliken för den aktuella artikeln. Alla serienummerrader har ett tomt serienummervärde och status **Inte registrerat**. Du kan skanna serienummerstreckkoder, eller välja **Serienummer** i appfältet för att kontinuerligt ange serienummer. Serienumren som du anger visas i listan och deras status ändras till **Registrerar**. Maximalt antal serienummer som du kan registrera i listan är lika med leveranskvantiteten. Om du gör fel kan du välja **Redigera** eller **Rensa** i fältet **Detaljer** för att ändra serienummer du har angett.

Du kan även registrera serienummer på fliken **Alla serialiserade artiklar** på sidan för **Hantering av serienummer**. I listan väljer du den artikel du vill registrera serienummer mot.

Om du vill kan du aktivera serienummer för tillgänglighetsvalidering under serienummer registreringen på en utgående överföringsorder. Om du försöker leverera ett serienummer som inte är tillgängligt i lagret för det här godkännandet, visas ett felmeddelande och du måste ange ett annat nummer.

Om du vill aktivera en sådan validering måste du schemalägga följande jobb så att de körs regelbundet:

- **Retail och Commerce** > **Retail och Commerce IT** > **Produkter och lager** > **Produkttillgänglighet med spårningsdimension**
- **Retail och Commerce** > **Distributionsscheman** > **1130** (**Produkttillgänglighet**)

## <a name="sell-serialized-items-in-pos"></a>Sälja serialiserade artiklar i POS

Även om kassaprogrammet alltid har haft stöd för serialiserade försäljningsartiklar, kan organisationer i Commerce version 10.0.17 och senare aktivera funktioner som utökar den affärslogik som utlöses när produkter som säljs är konfigurerade för serienummerspårning.

När funktionen **Förbättrad serienummervalidering i orderregistrering och -uppfyllelse i kassa** har aktiverats kommer följande produktkonfigurationer att bedömas när du säljer serialiserade produkter i POS:

- Konfiguration av **seriell typ** för produkten (**aktiv** eller **aktiv i försäljning**).
- **Tomt ärende tillåtet**-inställningar för produkten.
- **Fysiskt negativt lager**-inställningar för produkten och/eller säljande lagerställe.

### <a name="active-serial-configurations"></a>Aktiva konfigurationer av serienummer

När artiklar säljs i POS och har konfigurerats med en **aktiv** spårningsdimension för aktivt serienummer initierar POS valideringslogiken som förhindrar att användare slutför försäljningen av en serialiserad artikel med ett serienummer som inte finns i det säljande lagerställets aktuella lager. Det finns två undantag från denna valideringsregel:

- Om artikeln också konfigureras med **Tomt ärende tillåts** aktiverat, kan användarna hoppa över inmatningen av serienumret och sälja artikeln utan serienummer.
- Om artikeln och/eller det säljande lagerstället konfigureras med **Fysiskt negativt lager** aktiverat, godkänner och säljer programmet ett serienummer som inte kan bekräftas finnas i lagret på det lagerställe som den säljs mot. Denna konfiguration gör det möjligt att låta lagertransaktionen för det specifika artikel-/serienumret att bli negativt, varigenom systemet kan tillåta försäljning av okända serienummer.

> [!IMPORTANT]
> För att säkerställa att POS-programmet kan validera om serienummer som säljs för artiklar av **aktiv** serietyp finns i det säljande lagerstället, måste organisationer på frekvent basis köra jobbet **Produkttillgänglighet med spårning av dimensioner** i Commerce-administrationen och tillhörande distributionsjobb för produkttillgänglighet **1130** via Commerce-administrationen. När nytt serialiserat lager tas emot till lagerställen för försäljning, måste lagerledaren ofta uppdatera kanaldatabasen med de senast uppdaterade uppgifterna om lagertillgänglighet för de serienummer som säljs, detta för att POS ska kunna validera lagertillgänglighetsdata. Jobbet **Produkttillgänglighet med spårningsdimensioner** tar en aktuell ögonblicksbild av huvudlagret, inklusive serienummer, för alla företagets lagerställen. Distributionsjobbet **1130** tar ögonblicksbilden av lagret och delar den med alla konfigurerade kanaldatabaser.

### <a name="active-in-sales-process-serial-configurations"></a>Aktiv i seriekonfigurationer i försäljningsprocessen

Artiklar som konfigurerats med seriedimensionen **Aktiv i försäljningsprocess** går inte igenom någon lagervalideringslogik, detta eftersom denna konfiguration antyder att lagerserienumren inte är förregistrerade i lagret och att serienumren endast registreras in vid tidpunkten för försäljning.  

Om **Tomt ärende tillåtet** också har konfigurerats för **Aktiv i försäljningsprocess** kan inmatningen av serienumret hoppas över.. Om **Tomt ärende tillåtet** inte har konfigurerats kräver programmet att användaren anger ett serienummer, även om detta inte kommer att valideras mot tillgängligt lager.

### <a name="apply-serial-numbers-during-creation-of-pos-transactions"></a>Använd serienummer när du skapar POS-transaktioner

POS-programmet uppmanar omedelbart användare att samla in serienummer när de säljer en serialiserad artikel, men med programmet kan användarna hoppa över inmatningen av serienummer fram till en viss tidpunkt i försäljningsprocessen. När användaren börjar registrera betalning framtvingar och kräver programmet serienummerpost för alla artiklar som inte är konfigurerade att uppfyllas via framtida försändelser eller upphämtningar. Alla serialiserade artiklar som konfigurerats för hämtköp eller leverans kräver att användaren registrerar serienumret (eller går med på att lämna det tomt om artikelkonfigurationen tillåter det) innan försäljningen slutförs.

För serialiserade artiklar som säljs för framtida upphämtning eller leverans kan POS-användare initialt hoppa över att ange serienumret och ändå slutföra skapandet av kundordern.   

> [!NOTE]
> När du säljer eller uppfyller serialiserade produkter via POS-programmet tillämpas kvantiteten "1" på de serialiserade artiklarna i försäljningstransaktionen. Detta är ett resultat av hur serienummerinformationen spåras på försäljningsraden. När du säljer eller uppfyller en transaktion för flera serialiserade artiklar via POS, får varje försäljningsrad bara konfigureras med kvantiteten "1". 

### <a name="apply-serial-numbers-during-customer-order-fulfillment-or-pickup"></a>Använd serienummer vid uppfyllelse eller upphämtning av kundorder

När du uppfyller kundorderrader för serialiserade produkter med hjälp av åtgärden **Orderuppfyllelse** i POS, framtvingar POS registrering av serienumret före slutförande. Om ett serienummer inte tillhandahållits under den initiala orderinregistreringen måste det därför registreras under plock-, packnings- eller leveransprocesserna i POS. En validering görs vid respektive steg, och användaren uppmanas bara att bekräfta serienummerdata om dessa saknas eller är ogiltiga. Om en användare till exempel hoppar över plock- eller packningsstegen och startar en leverans, och ett serienummer inte har registrerats för raden, kräver POS att serienumret anges innan det slutgiltiga fakturasteget slutförs. När framtvingad registrering av serienumret under uppfyllelseoperationer av order i POS tillämpas, gäller fortfarande alla regler som omnämnts tidigare i det här avsnittet. Bara serialiserade artiklar som konfigurerats som **Aktiva** genomgår en lagervalidering för serienummer. Artiklar som konfigurerats som **Aktiva i försäljningsprocessen** kommer inte att valideras. Om **Fysiskt negativt lager** tillåts för **Aktiva** produkter, accepteras alla serienummer oavsett lagertillgänglighet. För såväl **Aktiva** artiklar som artiklar **Aktiva i försäljningsprovess** gäller, att om **Tomt ärende tillåtet** har konfigurerats, så kan en användare lämna serienumret tomt om så önskas i samband med stegen för plock, packning och leverans.

Validering av serienummer sker också när en användare utför upphämtningsåtgärder på kundorder i POS. POS-programmet tillåter inte att en hämtning slutförs på en serialiserad produkt såvida denna inte passerar valideringarna som tidigare nämns. Valideringarna baseras alltid på produktens spårningsdimension och säljande lagerställekonfiguration. 

## <a name="additional-resources"></a>Ytterligare resurser

[Inkommande lageråtgärder i POS](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)

[Utgående lageråtgärder i POS](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation)


[!INCLUDE[footer-include](../includes/footer-banner.md)]