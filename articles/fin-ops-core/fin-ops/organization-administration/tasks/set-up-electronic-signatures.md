---
title: Ställ in elektroniska signaturer
description: Använd den här proceduren för att konfigurera elektroniska signaturer.
author: maertenm
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysConfiguration, SIGParameters, SIGReasonCode, SIGProcSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4075e47013bb6a3f42cb07f88df121cef8688463cab25c4a734c5363106ace4c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749542"
---
# <a name="set-up-electronic-signatures"></a>Ställ in elektroniska signaturer

[!include [banner](../../includes/banner.md)]

Använd den här proceduren för att konfigurera elektroniska signaturer. En elektronisk signatur bekräftar identiteten hos en person som ska påbörja eller godkänna en dataprocess. Det demonstrationsdataföretag som används för att skapa den här proceduren är DAT.


## <a name="enable-the-electronic-signature-configuration-key"></a>Aktivera konfigurationsnyckeln för elektronisk signatur
1. Gå till Systemadministration > Inställningar > Licenskonfigurering.
2. Utöka Administration i trädet.
    * Kontrollera att kryssrutan Elektronisk signatur är markerad.  
    * Om kryssrutan Elektronisk signatur inte markeras måste du aktivera underhållsläge. Underhållsläget kan aktiveras i den här miljön genom att ett underhållsjobb körs från Lifecycle Services eller genom att verktyget Deployment.Setup används lokalt.  
3. Stäng sidan.

## <a name="set-up-electronic-signature-parameters"></a>Ställ in parametrar för elektroniska signaturer
1. Gå till Organisationsadministration > Inställningar > Elektronisk signatur > Parametrar för elektroniska signaturer.
2. Klicka på Redigera.
3. Ange ett värde i fältet Meddelande.
    * Ange det meddelande som ska visas för undertecknarna när en signatur begärs. Du kan ange vilken text du vill. I normalfallet beskriver denna text för användaren vad det innebär att signera ett dokument elektroniskt.  
    * Om du vill ange meddelandetexten på ytterligare språk, klicka på knappen Översättningar.  
4. Klicka på Spara.
5. Stäng sidan.

## <a name="set-up-reason-codes-for-electronic-signatures"></a>Ställ in orsakskoder för elektroniska signaturer
1. Gå till Organisationsadministration > Inställningar > Elektronisk signatur > Orsakskoder för elektronisk signatur.
2. Klicka på Ny.
    * Du måste ange orsakskoder innan du använder elektroniska signaturer. En giltig orsakskod krävs för att ett dokument ska kunna undertecknas.     En undertecknare väljer en orsakskod för att ange syftet med en elektronisk signatur. En orsakskod kan till exempel användas för att visa juridiskt godkännande.  
3. Skriv ett värde i fältet Orsak.
4. Ange ett värde i fältet Beskrivning.
    * Ange ytterligare orsakskoder, om det behövs.  
5. Klicka på Spara.
6. Stäng sidan.

## <a name="require-electronic-signatures-for-existing-processes"></a>Kräv elektroniska signaturer för befintliga processer
1. Gå till Organisationsadministration > Inställningar > Elektronisk signatur > Krav för elektroniska signaturer.
2. Hitta och markera önskad post i listan.
    * Välj en process som kräver elektroniska signaturer.  
3. Markera eller avmarkera kryssrutan Signatur krävs.
    * Upprepa de här stegen för de olika processer som kräver elektroniska signaturer.  
4. Klicka på Spara.

## <a name="create-a-custom-requirement-for-electronic-signatures"></a>Skapa ett anpassat krav för elektroniska signaturer
1. Klicka på Ny.
2. Markera eller avmarkera kryssrutan Signatur krävs.
3. I fältet Namn, ange ett namn för processen som kräver elektroniska signaturer.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tabellnamn.
5. I listan, sök efter och välj den tabell där de data som måste signeras är lagrade.
6. Klicka på länken på den valda raden i listan.
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Fältnamn.
8. I listan, hitta och välj det fält i registret som du vill övervaka.
9. Klicka på länken på den valda raden i listan.
    * Ange när en signatur är obligatorisk.     Välj Alltid om en signatur krävs när data i fältet ändras.     Välj Endast om du vill ange att en signatur enbart krävs under vissa förhållanden. Om du väljer Endast måste du även välja ett av följande alternativ: När en post infogas, När en post uppdateras eller När en post tas bort.  
10. Klicka på Spara.
11. Stäng sidan.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]