---
title: "Ställa in anläggningstillgångar"
description: "Det här avsnittet ger en översikt över Inställning av modul för anläggningstillgångar."
author: twheeloc
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13771
ms.assetid: 8be64197-fea1-4a34-8af2-d939919c28b1
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 8c772f9adf9a0f50cde62744f676da669936ff8e
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-fixed-assets"></a>Ställa in anläggningstillgångar

[!include[banner](../includes/banner.md)]


Det här avsnittet ger en översikt över Inställning av modul för anläggningstillgångar.

<a name="overview"></a>Översikt
--------
Parametrar styr det allmänna beteendet bland anläggningstillgångar.

Anläggningstillgångsgrupper låter dig gruppera dina tillgångar och ange standardinställningsattribut för varje tillgång som har tilldelats till en grupp. Böcker tilldelas till Anläggningstillgångsgrupper. Böcker följer det ekonomiska värdet för en anläggningstillgång över tid genom att använda avskrivningkonfigurationen som definieras i avskrivningsprofilen.

Anläggningstillgångar tilldelas en grupp när de skapas. Som standard kommer de böcker som har tilldelats Anläggningstillgångsgruppen sedan att tilldelas till anläggningstillgången. Böcker som har konfigurerats för bokföring i redovisningen associeras med en bokföringsprofil. Redovisningskonton definieras per bok i bokföringsprofilen, och används när transaktioner för anläggningstillgångar bokförs. 

![FixedAssetsComponentsImage](./media/FAComponents_Updated.png)

## <a name="depreciation-profiles"></a>Avskrivningsprofiler
Du bör skapa avskrivningsprofiler först. I avskrivningsprofilen konfigurerar du hur en tillgångs värde skrivs av över tid. Du måste definiera avskrivningsmetod, avskrivningsår (kalenderår eller räkenskapsår) och frekvensen för avskrivningen.

## <a name="books"></a>Böcker
När du har ställt in avskrivningsprofiler måste du skapa de nödvändiga böckerna för dina tillgångar. Varje bok följer en viss ekonomisk livscykel för en tillgång. Böcker kan konfigureras för att bokföra associerade transaktioner i redovisningen. Denna konfiguration utgör standardinställningen eftersom den normalt används för ekonomisk företagsrapportering. Böcker som inte bokför i redovisningen bokför endast i redovisningsjournaler för anläggningstillgångar och används som regel i momsrapporteringssyfte.

En primär avskrivningsprofil tilldelas varje bok. Böcker har också en alternativ eller profil för avskrivningsomställning, om denna profiltyp kan användas. För att automatiskt inkludera förteckningar över anläggningstillgångar i avskrivningskörningar måste du aktivera alternativet Beräkna avskrivning. Om detta alternativ inte markeras för en tillgång, hoppar avskrivningsförslaget över tillgången.

Du kan också ställa in härledda böcker. De angivna härledda transaktionerna bokförs som en exakt kopia av den primära transaktionen mot de härledda böckerna. Därför ställs härledda transaktioner vanligtvis in för anskaffningar och avyttringar, inte för avskrivningstransaktioner.

## <a name="fixed-asset-posting-profiles"></a>Bokföringsprofiler för anläggningstillgångar
När du har skapat böcker kan du skapa bokföringsprofilen. Bokföringsprofilen måste definieras av boken, men den kan också anges på en mer detaljerad nivå. Du kan till exempel definiera bokföringsprofilen för kombinationen av en bok och en Anläggningstillgångsgrupp, eller t.o.m för en enskild förteckning över anläggningstillgångar. Som standard används de redovisningskonton som har definierats för dina transaktioner för anläggningstillgångar.

Du måste definiera vilka huvudbokskonton som används under förfogandeprocesserna, både förfogandeförsäljningar och förfogandekassationer. Vid tidpunkten för avyttrande kommer de transaktioner för anläggningstillgångar som tidigare bokförts att återföras ut från de ursprungliga kontona, och nettobeloppen flyttas till lämpligt konto för resultaträkningen för avyttrande av tillgång. För att garantera att transaktioner återförs korrekt, måste du ställa in konton för varje typ av transaktion som du använder inom verksamheten. Huvudkontot ska vara det ursprungliga kontot som du anger för transaktionstypen i bokföringsprofilen, medan motkontot ska vara ditt vinst- och förlustkonto. Undantaget är bokfört nettovärde. I det här fallet bör både huvudkonto och motkonto anges till vinst och förlust för förfogandekonto.

## <a name="fixed-asset-groups"></a>Anläggningstillgångsgrupper
Anläggningstillgångsgrupp är det enda obligatoriska fältet när du skapar en anläggningstillgång. Värdet i det här fältet avgör förvalda värdet i flera informationsfält för tillgången. Böcker har ställts in så att en standardbok tilldelas till varje tillgång i en grupp. Du kan sedan ange bokattribut som är specifika för en grupp av tillgångar, till exempel tjänstelivslängd och avskrivningspraxis.

Du kan också definiera särskilda avskrivningar, eller bonusavskrivning, för en viss kombination av en Anläggningstillgångsgrupp och en bok. Du måste tilldela en prioritet till den särskilda avskrivningen för att registrera ordern som avdrag beräknas i, när flera avdrag tilldelas till en bok.

## <a name="fixed-asset-parameters"></a>Parametrar för anläggningstillgångar
Det sista steget är att uppdatera parametrarna för anläggningstillgångar.

Fältet Kapitaliseringströskel bestämmer de tillgångar som skrivs av. Om en inköpsrad markeras som en anläggningstillgång men inte uppfyller den angivna kapitaliseringströskeln, kommer en anläggningstillgång ändå att skapas eller uppdateras, men alternativet Beräkna avskrivning anges som Nei. Därför kommer tillgången inte automatiskt att skrivas av som en del av avskrivningsförslagen.

Ett viktigt alternativ är Skapa avskrivningsjusteringsbelopp med avyttring automatiskt. När du ställer in detta alternativ som Ja kommer tillgångsavskrivningen att justeras automatiskt, baserat på avskrivningsinställningarna vid tidpunkten då anläggningstillgången avyttras. Ett annat alternativ låter dig dra av kassarabatter från ditt anskaffningsbelopp när du införskaffar anläggningstillgångar genom en leverantörsfaktura.

I snabbfliken Inköpsorder kan du konfigurera hur dina tillgångar ska skapas som en del av inköpsprocessen. Det första alternativet är Allow asset acquisition from Purchasing. Om du ställer in detta alternativ som Ja, sker anskaffning när fakturan bokförs. Om du ställer in detta alternativ som Nej, kan du fortfarande infoga en anläggningstillgång på en inköpsorder (PO) och faktura, men anskaffningen bokförs inte. Bokföring måste utföras som ett separat steg från journalen för anläggningstillgångar. Alternativet Skapa tillgång under bokföring av produktinleverans eller faktura låter dig skapa en ny tillgång "i farten" i samband med bokföring, så att den inte måste skapas som en anläggningstillgång före transaktionen. Det sista alternativet, Sökning efter anläggningstillgångar som skapats vid radregistreringen gäller endast för inköpsrekvisitioner.

Du kan konfigurera orsakskoder så att dessa krävs för ändringar av en anläggningstillgång eller för specifika transaktioner för anläggningstillgångar.

Slutligen, på fliken Nummersekvenser, anger du nummerserier för anläggningstillgångar. Anläggningstillgångens nummerserie kan åsidosättas av Anläggningstillgångsgruppens nummerserie, om denna har angetts.




