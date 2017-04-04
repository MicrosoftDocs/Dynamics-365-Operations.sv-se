---
title: "Integrering av anläggningstillgångar"
description: "Anläggningstillgångar kan integreras med Redovisning, Lagerhantering, Kundreskontra och Leverantörsreskontra. Du kan också ställa in anläggningstillgångar så att detta integreras med inköpsorder."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3501
ms.assetid: f0639053-d99c-432a-8ead-5c26e0d4eaec
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: 9184e98c8afeef496aa709154d3bea26005fe611
ms.lasthandoff: 03/31/2017


---

# <a name="fixed-assets-integration"></a>Integrering av anläggningstillgångar

Anläggningstillgångar kan integreras med Redovisning, Lagerhantering, Kundreskontra och Leverantörsreskontra. Du kan också ställa in anläggningstillgångar så att detta integreras med inköpsorder.

<a name="general-ledger"></a>Huvudbok
--------------

I redovisningen sammanfattas värdet av alla anläggningstillgångar vanligtvis på flera huvudkonton som är nödvändiga för ekonomisk rapportering. Däremot kan du på sidan **Fixed assets** skapa många poster för anläggningstillgångar. Dessa poster kan innehålla information som anskaffningspriset, avskrivning och värderingen. Varje gång du bokför en transaktion för en anläggningstillgång uppdateras motsvarande huvudkonton. Huvudkontona för anläggningstillgångar innehåller alltid det uppdaterade värdet på anläggningstillgångarna.

På sidan **Fixed asset posting profiles** anger du de huvudkonton som transaktioner av böcker för anläggningstillgångar bokförs till. Du kan också specificera vilka typer av transaktioner med anläggningstillgångar som bokförs på varje bokföringskonto. Du kan skapa olika kombinationer av huvudkonton för anläggningstillgångar, beroende på detaljnivån som du vill använda för anläggningstillgångar i redovisningen. Huvudkonton kan baseras på transaktionstyper, böcker och andra huvudkonton.

## <a name="inventory-management"></a>Lagerhantering
I lagerjournalen för anläggningstillgångar kan du ange anskaffningen av anläggningstillgångar som den juridiska personen har producerat eller skapat åt sig själv. Du kan sedan överföra lagerartiklar till anläggningstillgångar antingen som en anskaffning eller som en del av en anskaffning. 

Du kan också anskaffa tillgångar med inköpsorder. När inköpsorder innehåller lagerartiklar som betecknas som anläggningstillgångar, bestämmer inställningen **Allow asset acquisition from Purchasing** på sidan **Fixed assets parameters** om anskaffningen bokförs för anläggningstillgången när fakturan bokförs. Vilken effekt som anskaffningen av anläggningstillgångar har på lagret beror på konfigurationen av den juridiska personen. 

När en lagerartikel blir en anskaffning av en anläggningstillgång genom lagerjournalen, en inköpsorder eller ett anskaffningsförslag, skapas en anskaffningstransaktion för anläggningstillgångsboken. Om en bokanskaffning inkluderar en härledd bok, skapas också en anskaffningstransaktion för den härledda boken. 

Bokföringsregler som skapas på sidan **Posting** i lagerhanteringen styr minskningen i lager när en anskaffning bokförs. Du måste emellertid inte alltid minska lagret när du bokför fakturor som hör till anläggningstillgångar. I vissa fall kanske anläggningstillgångarna köps in för intern användning. Ett exempel är en bärbar dator som köps in för försäljningsavdelningen. När du arbetar med inköpsorder kan du använda artiklar som har ställts in för både återförsäljning och internt bruk. 

Om du använder särskilda inleverans- och utleveranskonton för anläggningstillgångar i artikelgrupper, kan du använda samma lagerartikel för både interna inköp och som lager för återförsäljning. 

Anläggningstillgångar som är till för internt bruk skapas så att de har kontotypen **Fixed asset receipt**. Den här kontotypen används för att spåra mottagandet av anläggningstillgången. När du bokför en leverantörsfaktura ska du använda kontot för inleverans av anläggningstillgångar om något av följande villkor är sant:

-   Fakturaraden innehåller en befintlig anläggningstillgång för internt bruk.
-   Kryssrutan **New fixed asset?** är markerad för den produktinleveransrad som har bokförts.
-   Kryssrutan för **Create a new fixed** asset markeras för leverantörsfakturaraden.

Detta konto är vanligtvis ett utgiftskonto. Du kan ställa in kontotypen **Fixed asset receipt** för en artikelgrupp eller en enskild artikel med hjälp av fliken **Purchase order** på sidan **Item group** eller **Posting**.

På samma sätt kan anläggningstillgångar som är till för internt bruk skapas så att de har kontotypen **Fixed asset issue**. Den här kontotypen används för att spåra utfärdandet av anläggningstillgången till mottagaren. När en tillgång anskaffas med hjälp av en försäljningsorder, fungerar utleveranskontot för anläggningstillgångar som motkonto till anläggningstillgångens debetkonto. Tillgångsanskaffningen kan bokföras när du bokför en leverantörsfaktura eller när du bokför tillgångsanskaffningen i journalen för anläggningstillgångar, eventuellt genom att använda ett anskaffningsförslag. Du kan ställa in kontotypen **Fixed asset issue** för en artikelgrupp eller en enskild artikel med hjälp av fliken **Inventory** på sidan **Item group** eller **Item posting**. 

Slutligen bestäms huvudkontona som används för bokföring av alternativen för redovisningsintegrering som anges för artikelmodellgruppen. Vilka huvudkonton som används varierar beroende på om en tillgång har tilldelats till inköpsorderraden. Kontona härleds från bokföringsprofilen för respektive artikelgrupp. 
**Obs!** Om det finns en lagerreservation när produktinleveranser bokförs, kan du inte tilldela en anläggningstillgång eller skapa en anläggningstillgång från raden. 

Vilka konton som transaktioner för anläggningstillgångar bokförs till beror på två faktorer: om tillgångarna köps in eller skapas av den juridiska personen, samt på tillgångens transaktionstyp. 

Transaktionstypen kopplar lagertransaktionen till bokföringsprofilen i anläggningstillgångar. Eftersom bokföringsprofilen i anläggningstillgångar anger vilka konton som ska uppdateras är valet av en transaktionstyp för en anläggningstillgång indirekt också ett val av vilka huvudkonton transaktionen ska bokföras till. För både konstruerade och köpta anläggningstillgångar är transaktionstypen vanligtvis **Acquisition** eller **Acquisition adjustment**.

## <a name="accounts-receivable"></a>Kundreskontra
En integration av Anläggningstillgångar med Kundreskontra använder bokföringsprofiler som har ställts in i Anläggningstillgångar. Dessa bokföringsprofiler aktiveras när en anläggningstillgång, bok eller transaktionstyp för anläggningstillgång markeras för en kundfaktura innan kundfakturan bokförs. Eftersom anläggningstillgångar inte är en del av Lagerhantering måste du använda sidan **Free text invoice** när du säljer en anläggningstillgång. 

Om värdemodellen innehåller en härledd bok skapas den härledda boktransaktionen när du bokför kundfakturan.

## <a name="accounts-payable"></a>Leverantörsreskontra
Anläggningstillgångar anskaffas vanligtvis från externa leverantörer. Du kan använda sidan **Fixed assets parameters** för att ange om tillgångsanskaffningar alltid ska bokföras när du bokför leverantörsfakturor, eller om tillgångsanskaffningar bara kan bokföras från anläggningstillgångar. Om du möjliggör att anskaffningar av tillgångar bokförs från leverantörsreskontra, uppdateras anläggningstillgångskontona när en leverantörsfaktura för en anläggningstillgångsanskaffning bokförs. 

Om systemet är inställt på att bokföra en tillgångsanskaffning när en faktura bokförs, bokförs transaktionen enligt de bokföringsprofiler som ställts in i Anläggningstillgångar för de olika transaktionstyperna för anläggningstillgångar. Bokföringen styrs av anläggningstillgången, boken och transaktionstypen för anläggningstillgången som väljs på sidan **Purchase order** innan leverantörsfakturan bokförs. 

Om boken innehåller en härledd bok skapas den härledda boktransaktionen när du bokför leverantörsfakturan.

Integreringen för respektive orderrad på fliken **Fixed assets** på snabbfliken **Line details** på sidan **Purchase order**. Du kan skicka en inköpsorder för en anläggningstillgång till leverantören. Anläggningstillgångarna och huvudkontona uppdateras dock bara när du bokför leverantörsfakturan efter att anläggningstillgången tagits emot. Eftersom inköpsorder bara kan innehålla lagerartiklar beror effekten som anskaffningen av anläggningstillgångar har på lagret på inställningen av den juridiska personen.

## <a name="project-management-and-accounting"></a>Projekthantering och redovisning
Du kan associera ett projekt med en tillgång som påverkas av projektet. Du kan också associera respektive fas, uppgift eller delprojekt till en annan tillgång. En tillgång kan kopplas till varje projektpost. Du skapar associationen när du registrerar ett anläggningstillgångsnummer i nummerfältet **Fixed asset** på sidan **Projects**. Projekttypen måste vara antingen **Internal** eller **Cost project**. 

Du kan också använda sidan **Projects** när du vill visa detaljer om tillgångarna som associeras med projekt. Om du vill visa anläggningstillgångsposten: På snabbfliken **Setup** klickar du på länken för att öppna sidan **Fixed assets**. Klicka på **projekt**&gt;**alla projekt** om du vill visa projekten som associeras med anläggningstillgången. 

Vanligtvis associerar du anläggningstillgångar med projekt när projekten berör arbete, underhåll eller förbättringar av tillgången. När projektet är klart skapas ingen uppskrivningsjustering av tillgången automatiskt. Därför måste du manuellt skapa uppskrivningen, om en justering krävs. 

Du tar bort kopplingen mellan ett projekt och en tillgång genom att avmarkera fältet **Fixed asset number** på sidan **Projects** page. 

Du kan också beteckna en anläggningstillgång som du skapar eller tillverkar inom ett uppskattningsprojekt. I slutet av uppskattningsprojektet kan du automatiskt bokföra en anskaffningstransaktion för tillgången.

Mer information finns i [förvärv av tillgångar genom inköp](acquire-assets-procurement.md)

