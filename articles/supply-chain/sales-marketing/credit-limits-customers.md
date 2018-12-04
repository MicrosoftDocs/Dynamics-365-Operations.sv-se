---
title: "Kreditgränser för kunder"
description: "Denna vara innehåller en översikt över hur kreditgränser fungerar i Microsoft Dynamics 365 for Finance and Operations."
author: omulvad
manager: AnnBe
ms.date: 09/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e00828ea24434da6dfd7443153b007ea728375f3
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="credit-limits-for-customers"></a>Kreditgränser för kunder

[!include [banner](../includes/banner.md)]

Med en kreditgräns kan du ange maxgränsen för den kredit du beviljar dina kunder. Om en kreditgräns har angetts, kommer denna att kontrolleras automatiskt när en användare försöker uppdatera ett dokument. Om kreditgränsen överskrids visas ett meddelande för användaren. Den här varan innehåller en översikt över hur kreditgränser fungerar och besvarar följande frågor:

-   Vilka dokument och processer kan jag kontrollera kreditgränsen för?

-   Var konfigurerar jag hur kundens återstående kredit beräknas?

-   Var används information om kundens återstående kredit?

-   Var anger jag huruvida identifiering krävs för att kredit ska beviljas till en kund, och även vilket kreditbelopp som kräver identifiering?

-   Var anger jag huruvida en varning eller ett felmeddelande ska visas om kreditgränsen överskrids?

-   Hur jag för att ange kreditgränsen för en viss kund?

-   Hur kontrollerar jag kreditgränser manuellt på försäljningsorder?

**Vilka dokument och processer kan jag kontrollera kreditgränsen för?**

Använd formuläret **Parametrar för kundreskontra** för att ange vilka dokument du vill kontrollera kreditgränserna för. Du måste inneha säkerhetsrollen som systemadministratör (- SYSADMIN-) för att göra ändringar i det här formuläret. Du kan kontrollera kreditgränser för följande dokument och processer:

-   Fakturor för försäljningsorder, när du bokför fakturor

-   Följesedlar för försäljningsorder, när du uppdaterar följesedlar

-   Försäljningsorder när du lägger till rader i formuläret **Försäljningsorder**

-   Försäljningsorder, när dessa skapas via en tjänst

-   Fritextfakturor, när du bokför fakturorna

Kreditgränserna kontrolleras automatiskt om något av följande alternativ har angetts:

-   I formuläret **Parametrar för kundreskontra** anges fältet **Kreditgränsens typ** till vad som helst förutom **Ingen**. Kreditgränserna kontrolleras för alla kunder.

-   I fältet **Parametrar för kundreskontra** anges fältet **Kreditgränstyp** som **Ingen**, men **Obligatorisk kreditgräns** har valts för en kund i formuläret **Kunder**. Kreditgränserna kontrolleras endast för vissa kunder.

Om du vill kontrollera kreditgränserna för följande dokument, måste du ange ytterligare inställningar.

|    Dokument                                    |    Ytterligare inställningar                                                                                                             |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
|    Fritextfaktura                         |    Välj Kontrollera kreditgräns på fritextfaktura bland parametrarna för kundreskontra, i området för kreditbedömning.     |
|    Försäljningsorder (anges manuellt)            |    Välj Kontrollera kreditgräns på försäljningsfaktura bland parametrarna för kundreskontra, i området för kreditbedömning.           |
|    Försäljningsorder (elektroniskt mottagen)     |    Välj Kontrollera kreditgräns för försäljningsorder bland parametrarna för kundreskontra, i området för AIF.                     |

**Var konfigurerar jag hur den återstående krediten för en kund beräknas?**

Du kan konfigurera Dynamics 365 i syfte att beräkna kundens återstående kredit på något av följande sätt:

-   Jämför kreditgränsen mot kundsaldot.

-   Jämför kreditgränsen med beloppen för kundbalans och följesedel.

-   Jämför kreditgränsen med kundbalansen och alla öppna transaktioner. Detta inkluderar beloppen på följesedel och försäljningsorder.

Använd formuläret **Parametrar för kundreskontra** för att ange vilken information som ska jämföras med. Du måste inneha säkerhetsrollen som systemadministratör (- SYSADMIN-) för att göra ändringar i det här formuläret. I fältet **Kreditgränstyp** väljer du om du vill utföra en kreditgränskontroll samt vilken transaktionsinformation som ska inkluderas när Kreditgränsen kontrolleras. Välj bland följande alternativ:

-   **Ingen** – Kontrollera inga kreditgränser. Du kan åsidosätta detta alternativ för en viss kund genom att välja kryssrutan **Obligatorisk kreditgräns** i formuläret **Kunder**. Om du gör detta kommer kreditgränsen att kontrolleras mot kundsaldot.

-   **Saldo** – Kreditgränsen kontrolleras mot kundsaldot.

-   **Saldo+följesedel eller produktinleverans** – Kreditgränsen kontrolleras mot kundsaldot och leveranserna.

-   **Saldo+Alla** – Kreditgränsen kontrolleras mot kundsaldot, leveranser och öppna order.

**Var används information om kundens återstående kredit?**

Information om kundens saldo och återstående kredit beräknas och sparas när du skapar en ögonblicksbild av åldersfördelningen, och visas i formuläret **Samlingar**. De belopp som visas i formuläret **Samlingar** kanske inte innehåller alla transaktionsaktiviteter tills en ny ögonblicksbild av åldersfördelningen skapas. Mer information finns i [Inkasso och kredit i kundreskontra](https://technet.microsoft.com/en-us/library/hh209221.aspx).

Information om kundens saldo och återstående kredit beräknas beroende på dokumenten som väljs när försäljningsorder, kundens fakturor och följesedlar ska uppdateras. Om beloppet för det dokument som du arbetar med orsakar att kreditgränsen överskrids, visas ett meddelande.

**Var anger jag huruvida identifiering krävs för att kredit ska beviljas till en kund, och även vilket kreditbelopp som kräver identifiering?**

Använd formuläret **Parametrar för kundreskontra** för att ange om du vill begära identifiering och den kreditgräns som kräver identifiering.
Du måste inneha säkerhetsrollen som systemadministratör (- SYSADMIN-) för att göra ändringar i det här formuläret.

|    Fält                                    |    beskrivning                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|---------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Kräv identifiering vid kredit     |    Välj den typ av ID/legitimation som måste anges för kunder som din organisation ger kredit till. Det alternativ som du väljer i detta fält bestämmer när och vilken typ av information som krävs i fälten för myndighets-ID i formuläret Kunder: Nej – Ingen myndighetsutfärdad legitimation/ID-information krävs, oavsett kundens kreditgräns.     Ja – Ett myndighetsutfärdat personnummer eller annan myndighetsutfärdad ID-handling krävs om kundens kreditgräns är större än eller lika med noll.     Minimigräns – Ett myndighetsutfärdat personnummer eller annan myndighetsutfärdad ID-handling krävs om kundens kreditgräns är större än eller lika med den gräns som du har angett i fältet Gräns i det här formuläret.        |
|    Justeringsgräns                                    |    Ange den kreditgräns som innebär att ett myndighetsutfärdat personnummer eller annan ID-information krävs för kunder.    Skriv till exempel 2 000 om du vill att ett legitimations-/ID-nummer, t.ex. ett körkortsnummer, ska anges för alla kunder med en kreditgräns som är lägst 2 000.    Det här fältet är tillgängligt om du har valt Minimigräns i fältet Kräv ID vid kredit.                                                                                                                                                                                                                                                                                                                                                                                                                                         |

**Var anger jag huruvida en varning eller ett felmeddelande ska visas om kreditgränsen överskrids?**

Använd formuläret **Parametrar för kundreskontra** för att ange om du vill visa en varning eller ett felmeddelande om kreditgränsen överskrids. Denna varning eller ett fel visas när en användare anger eller bokför information, eller ingår i en logg om dokumenten bearbetas av en elektronisk tjänst. Du måste inneha säkerhetsrollen som systemadministratör (- SYSADMIN-) för att göra ändringar i det här formuläret.

|    Fält                                                               |    beskrivning                                                                                                                                                                                                                                                                                                                                                                                        |
|------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Meddelande när kreditgränsen överskrids (i området för kreditbedömning)     |    Välj hur meddelanden om kreditgränser överskrids visas för användarna. Välj bland följande alternativ: Fel – Ett felmeddelande visas. Detta stoppar vanligtvis den pågående åtgärden, och tvisten måste lösas innan processen kan fortgå.     Varning – Ett varningsmeddelande visas, men processen kan fortgå.                     |
|    Meddelande när kreditgränsen överskrids (i AIF-området)               |    Välj hur meddelanden om överskridande av kreditgräns ska levereras i en logg: Välj bland följande alternativ: Fel – Ett felmeddelande visas i formuläret Undantag, och dokumentet kommer inte att behandlas förrän felet har lösts.     Varning – Ett varningsmeddelande visas i formuläret Undantag, men processen kan fortgå.        |

**Hur gör jag för att ange kreditgränsen för en viss kund?**

Använd formuläret **Kunder** för att ange kreditgränsbeloppet för en viss kund. Du måste inneha en säkerhetsroll som har tilldelats tjänsten Behåll kundhuvud (CustCustomersMaintain) för att utföra ändringar i det här formuläret.

1.  Klicka på **Kundreskontra** \> **Allmänt** \> **Kunder** \> **Alla kunder**. Dubbelklicka på ett kundkonto.

2.  I formuläret **Kunder**, klicka på **Redigera** i åtgärdsfönstret.

3.  Ange valutabeloppet i fältet **Kreditgräns**. Detta värde måste vara större än noll (0) och kommer att användas som kreditgränsbelopp.

4.  Ange ett personnummer eller likvärdig myndighetsutfärdad ID-information i fältet **Myndighetsutfärdad identifiering** vid behov.

> [!NOTE]
> En kreditgränstyp väljs vanligtvis i formuläret **Parametrar för kundreskontra**. Om kreditgränstypen emellertid är inställd på **Ingen** måste du också markera kryssrutan **Obligatorisk kreditgräns** i formuläret **Kunder** för att kontrollera kundens kreditgräns mot kundens saldo. Mer information om olika typer av kreditgränser, se ”Vilka dokument och processer kan jag kontrollera kreditgränsen för”? i det här avsnittet. 

**Hur kontrollerar jag kreditgränser på försäljningsorder manuellt?**

Ibland kan behöva du kontrollera en kunds kreditgräns manuellt. Du kan exempelvis manuellt kontrollera en kunds kreditgräns innan du börjar ange en försäljningsorder. Du kan använda formuläret **Försäljningsorder** för att kontrollera kreditgränser manuellt. Du måste inneha en säkerhetsroll som har tilldelats tjänsten Behåll säljorder (CustCustomersMaintain) för att utföra ändringar i det här formuläret.

1.  Klicka på **Försäljning och marknadsföring** \> **Allmänt** \> **Försäljningsorder** \> **Alla försäljningsorder**. Dubbelklicka på en försäljningsorder.

2.  I formuläret **Försäljningsorder**, i fliken **Hantera** i åtgärdsfönstret, klickar du på **Kontrollera kreditgräns**.

