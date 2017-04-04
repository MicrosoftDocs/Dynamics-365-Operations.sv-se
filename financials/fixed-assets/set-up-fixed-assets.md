---
title: "Ställa in anläggningstillgångar"
description: "Det här avsnittet ger en översikt över Inställning av modul för anläggningstillgångar."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: b41901d573e977a89fcd1a7c1ebf7185e162c654
ms.openlocfilehash: dde8053df96d03c8c8e52fa6d2fdf7f74e95ec92
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-fixed-assets"></a>Ställa in anläggningstillgångar

Det här avsnittet ger en översikt över Inställning av modul för anläggningstillgångar.

<a name="overview"></a>Översikt
--------
Parametrar styr det allmänna beteendet bland anläggningstillgångar.

Anläggningstillgångsgrupper låter dig gruppera dina tillgångar och ange standardinställningsattribut för varje tillgång som har tilldelats till en grupp. Böcker tilldelas till anläggningstillgångsgrupper. Böcker följer det ekonomiska värdet för en anläggningstillgång över tid genom att använda avskrivningkonfigurationen som definieras i avskrivningsprofilen.

Anläggningstillgångar tilldelas en grupp när de skapas. Som standard kommer de böcker som har tilldelats anläggningstillgångsgruppen sedan att tilldelas till anläggningstillgången. Böcker som har konfigurerats för bokföring i redovisningen associeras med en bokföringsprofil. Redovisningskonton definieras per bok i bokföringsprofilen, och används när transaktioner för anläggningstillgångar bokförs. 

![FixedAssetsComponentsImage](./media/FAComponents_Updated.png)

## <a name="depreciation-profiles"></a>Avskrivningsprofiler
Du bör skapa avskrivningsprofiler först. I avskrivningsprofilen konfigurerar du hur en tillgångs värde skrivs av över tid. Du måste definiera avskrivningsmetod, avskrivningsår (kalenderår eller räkenskapsår) och frekvensen för avskrivningen.

## <a name="books"></a>Böcker
När du har ställt in avskrivningsprofiler måste du skapa de nödvändiga böckerna för dina tillgångar. Varje bok följer en viss ekonomisk livscykel för en tillgång. Böcker kan konfigureras för att bokföra associerade transaktioner i redovisningen. Denna konfiguration är standardinställningen, eftersom används vanligtvis för företagets redovisning. Regler som inte bokför i redovisningen bara bokföra anläggningstillgång redovisningsjournal och används för momsrapportering.

En primär avskrivningsprofil tilldelas varje bok. Böcker har också en alternativ eller profil för avskrivningsomställning, om denna profiltyp kan användas. För att automatiskt inkludera förteckningar över anläggningstillgångar i avskrivningskörningar måste du aktivera alternativet Calculate depreciation . Om det här alternativet inte har markerats för en tillgång avskrivningsförslaget hoppar över tillgången.

Du kan också ställa in härledda böcker. De angivna härledda transaktionerna bokförs som en exakt kopia av den primära transaktionen mot de härledda böckerna. Därför ställs härledda transaktioner vanligtvis in för anskaffningar och avyttringar, inte för avskrivningstransaktioner.

## <a name="fixed-asset-posting-profiles"></a>Bokföringsprofiler för anläggningstillgångar
När du har skapat böcker kan du skapa bokföringsprofilen. Bokföringsprofilen måste definieras av boken, men den kan också anges på en mer detaljerad nivå. Du kan till exempel definiera bokföringsprofilen för kombinationen av en bok och en anläggningstillgångsgrupp, eller t.o.m för en enskild förteckning över anläggningstillgångar. Som standard används de redovisningskonton som har definierats för dina transaktioner för anläggningstillgångar.

Du måste definiera vilka huvudbokskonton som används under förfogandeprocesserna, både förfogandeförsäljningar och förfogandekassationer. Vid tidpunkten för avyttrande kommer de transaktioner för anläggningstillgångar som tidigare bokförts att återföras ut från de ursprungliga kontona, och nettobeloppen flyttas till lämpligt konto för resultaträkningen för avyttrande av tillgång. För att garantera att transaktioner återförs korrekt, måste du ställa in konton för varje typ av transaktion som du använder inom verksamheten. Huvudkontot ska vara det ursprungliga kontot som du anger för transaktionstypen i bokföringsprofilen, medan motkontot ska vara ditt vinst- och förlustkonto. Undantaget är bokfört nettovärde. I det här fallet bör både huvudkonto och motkonto anges till vinst och förlust för förfogandekonto.

## <a name="fixed-asset-groups"></a>Anläggningstillgångsgrupper
Fixed asset group är det enda obligatoriska fältet när du skapar en anläggningstillgång. Värdet i det här fältet avgör förvalda värdet i flera informationsfält för tillgången. Böcker har ställts in så att en standardbok tilldelas till varje tillgång i en grupp. Du kan sedan ange bokattribut som är specifika för en grupp av tillgångar, till exempel tjänstelivslängd och avskrivningspraxis.

Du kan också definiera särskilda avskrivningar, eller bonusavskrivning, för en viss kombination av en anläggningstillgångsgrupp och en bok. Du måste tilldela en prioritet till den särskilda avskrivningen för att registrera ordern som avdrag beräknas i, när flera avdrag tilldelas till en bok.

## <a name="fixed-asset-parameters"></a>Parametrar för anläggningstillgångar
Det sista steget är att uppdatera parametrarna för anläggningstillgångar.

Fältet Capitalization threshold bestämmer de tillgångar som skrivs av. Om en inköpsrad väljs som en anläggningstillgång, men den inte uppfyller en angiven kapitaliseringströskel, en anläggningstillgång ändå skapas eller uppdateras, men alternativet Beräkna avskrivning har värdet Nej. Därför skrivas inte tillgången automatiskt som en del av avskrivningsförslag.

Ett viktigt alternativ är Automatically create depreciation adjustment amounts with disposal. När du ställer in detta alternativ som Yes kommer tillgångsavskrivningen att justeras automatiskt, baserat på avskrivningsinställningarna vid tidpunkten då anläggningstillgången avyttras. Ett annat alternativ låter dig dra av kassarabatter från ditt anskaffningsbelopp när du införskaffar anläggningstillgångar genom en leverantörsfaktura.

I snabbfliken Purchase orders kan du konfigurera hur dina tillgångar ska skapas som en del av inköpsprocessen. Det första alternativet är Allow asset acquisition from Purchasing. Om du ställer in detta alternativ som Yes, sker anskaffning när fakturan bokförs. Om du ställer in detta alternativ till Nej kan du ändå placera en anläggningstillgång på en inköpsorder (PO) och en faktura, men förvärvet inte kan bokföras. Bokföring måste utföras som ett separat steg från journalen för anläggningstillgångar. Skapa tillgången vid produktinleverans eller fakturera kan du skapa en ny tillgång "i farten" vid bokföring så att den inte behöver konfigureras som en anläggningstillgång innan transaktionen. Det sista alternativet, Check for fixed assets creation during line entry gäller endast för inköpsrekvisitioner.

Du kan konfigurera orsakskoder så att dessa krävs för ändringar av en anläggningstillgång eller för specifika transaktioner för anläggningstillgångar.

Slutligen, på fliken Number sequences, anger du nummerserier för anläggningstillgångar. Anläggningstillgångens nummerserie kan åsidosättas av anläggningstillgångsgruppens nummerserie, om denna har angetts.

