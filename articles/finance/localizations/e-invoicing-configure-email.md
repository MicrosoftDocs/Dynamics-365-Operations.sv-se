---
title: Konfigurera en e-postkanal
description: I denna artikel beskrivs hur du konfigurerar en e-postkanal för mottagning av e-fakturor.
author: gionoder
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 19339cbcc59e93289609690363b0dd9195a66f6e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279883"
---
# <a name="configure-an-email-channel"></a>Konfigurera en e-postkanal

[!include [banner](../includes/banner.md)]

Om den funktion för e-fakturering som du skapat importerar elektroniska leverantörsfakturor från bifogade filer som tas emot via e-post, bör du konfigurera en kanal för e-postkonto.

1. I Regulatory Configuration Service (RCS) väljer du den funktion för e-fakturering som du skapade. Se till att du väljer den version som har statusen **Utkast**.
2. På fliken **Inställningar** väljer du **Lägg till**.
3. I listrutedialogen **Skapa funktionsinställning**, i fältgruppen **Ny**, väljer du alternativet **Anpassade inställningar**.
4. I fältgruppen **Installationstyp** väljer du alternativet **Datakanal**.
5. I fältet **Välj datakanal** anger du **Inkommande e-post**.
6. Markera **Skapa**.
7. Markera den rad som du skapade tidigare och välj sedan **Redigera**.
8. På fliken **Datakanal**, i avsnittet **Parametrar**, ställer du in följande obligatoriska fält.

    | Fält                | Beskrivning |
    |----------------------|-------------|
    | Datakanal         | Ange ett unikt namn för att identifiera datakanalen. Namnet kan ha maximalt 10 tecken. Detta kommer att refereras till i tillämplighetsreglerna och i anslutna program under kommunikationsprocessen. |
    | Serveradress       | Ange serveradressen för e-postkontoprovidern. Serveradressen för providern `https://outlook.live.com` är till exempel imap-mail.outlook.com. |
    | Serverport          | Ange numret på den port som e-postkontoprovidern använder. Serverporten för providern `https://outlook.live.com` är exempelvis 993. |
    | Användarnamn hemligt     | Ange namnet på den nyckelvalvshemlighet för Microsoft Azure som innehåller ID:t för användarkontot för e-post. Denna hemlighet måste skapas i Key Vault och konfigureras i din tjänstemiljö. |
    | Användarens lösenord hemligt | Ange namnet på den nyckelvalvshemlighet som innehåller lösenordet för användarkontot för e-post. |
    | Tidsgräns              | Den maximala tidsgräns i millisekunder (ms) som systemet ska vänta på ett svar. Standardvärdet är 10 000 ms (10 sekunder). |
    | Huvudmapp          | Ange källan för e-postimporten eller mappen som tjänsten ska bearbeta e-postmeddelanden från. |
    | Arkivmapp       | Ange mappen där bearbetade e-postmeddelanden ska lagras. Om du inte anger den här mappen skapar systemet den automatiskt. |
    | Mappfel         | Ange den mapp dit systemet ska flytta e-postmeddelandena till om bearbetningen misslyckas. Om du inte anger den här mappen skapar systemet den automatiskt. |
    | Max meddelandestorlek     | Ange den maximala storleken, i byte, för ett enda meddelande som bearbetas. Standardvärdet är 20 000 000 byte. |
    | Max meddelandenummer   | Ange det maximala antal meddelanden som ska bearbetas för en enda åtgärd. Om du inte vill begränsa antalet meddelanden ställer du in värdet på **0** (noll). |
    | Från filter          | Ange en sträng för att filtrera after avsändaradress. Endast e-postmeddelanden där avsändaradressen matchar filtret bearbetas. Det här fältet är valfritt. Om du vill ange flera avsändaradresser använder du semikolon (;) som avgränsare. |
    | Ämnesfilter       | Ange en sträng för att filtrera after ämne. Endast e-postmeddelanden där ämnet matchar filtret bearbetas. Det här fältet är valfritt. En enkel mask såsom **\*smth\*.ext** stöds, där varje asterisk (\*) representerar noll eller fler förekomster av något tecken. |
    | Datumfilter          | Ange ett datum för att definiera den högsta åldern (i dagar) för meddelanden som bearbetas. Det här fältet är valfritt. Standardvärdet är 30 dagar. |
    | Bearbetningsläge      | <p>Välj ett av följande alternativ om du vill ange om alla bilagor i ett e-postmeddelande ska kunna bearbetas tillsammans eller om varje bilaga ska bearbetas separat:</p><ul><li><b>Efter bilaga</b> – Ett nytt elektroniskt dokument skapas för varje bilaga i e-postmeddelandet. Om ett e-postmeddelande till exempel innehåller flera filer som innehåller e-fakturadata, betraktas varje fil som en ny e-faktura i systemet.</li><li><b>Efter e-post</b> – En bilaga betraktas som en grundbilaga, och en (1) e-faktura skapas i systemet. Övriga bilagor kan användas som stödfiler.</li></ul> |

9. I avsnittet **Bilagefilter** lägger du till filfiltreringsinformationen. Endast bilagor som uppfyller det definierade filtret bearbetas. **\*.xml** filtrerar exempelvis för bilagor med filnamnstillägget .xml. Namnet på bilagan används i Dynamics 365 Finance eller Dynamics 365 Supply Chain Management under konfiguration.

    - Om du ställer in fältet **Bearbetningsläge** på **Efter e-post** i föregående steg kan du lägga till flera filter här. Namnet identifierar det specifika dokumentet.
    - Om du ställer in fältet **Bearbetningsläge** som **Efter bilaga** kan du bara lägga till ett (1) filter.

10. På fliken **Tillämplighetsregler** kan du granska och uppdatera kriterierna efter behov. Värdet i fältet **Kanal** måste vara lika med värdet som du angav i fältet **Datakanal** i steg 8.
11. Markera **Spara** och stäng sedan sidan.
