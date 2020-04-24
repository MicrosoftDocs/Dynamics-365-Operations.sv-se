---
title: Godkänn och bekräfta inköpsorder
description: Det här avsnittet innehåller en beskrivning av de statusar en inköpsorder genomgår efter att de har skapats och effekterna av att aktivera ändringshantering för inköpsorder.
author: mkirknel
manager: tfehr
ms.date: 04/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 93143
ms.assetid: cd12a944-c52c-4579-a301-7abe1d237c72
ms.search.region: Global
ms.search.industry: ''
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6b331b7e7725b3dd284deb02e59fcf2d699822c4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208004"
---
# <a name="approve-and-confirm-purchase-orders"></a>Godkänn och bekräfta inköpsorder

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en beskrivning av de statusar en inköpsorder (IO) genomgår efter att de har skapats och effekterna av att aktivera ändringshantering för inköpsorder.

När du har skapat en inköpsorder (IO) kan den behöva genomgå en godkännandeprocess. När leverantören har godkänt ordern sätts statusen för inköpsordern till **Bekräftad**.

## <a name="approval-of-purchase-orders"></a>Godkänna inköpsorder
Inköpsorder som inte använder ändringshantering har statusen **Godkänd** så fort den har skapats medan inköpsorder som använder ändringshantering har statusen **Utkast** när den skapas. En inköpsorder som har skapats via en bekräftelse av en planerad order från huvudplaneringen får alltid statusen **Godkänd**, oberoende av inställningarna för ändringshanteringen. En inköpsorder kan bara skapa lagertransaktioner när den har statusen **Godkänd**. Av den anledningen visas inte lagret som tillgängligt för reservation eller märkning förrän ordern har accepterats.

Du kan aktivera ändringshantering för inköpsorder genom att ställa in alternativet **Aktivera ändringshantering** på sidan **Anskaffnings- och källparametrar**. När ändringshantering är aktiverad måste inköpsorder genomgå ett godkännandearbetsflöde efter att de har slutförts. Supply Chain Management har en redigerare för arbetsflödesprocesser i vilken du kan definiera ett arbetsflöde som representerar din godkännandeprocess. Arbetsflödet kan omfatta regler för automatiskt godkännande, regler som fastställer vem som ska godkänna särskilda inköpsorder och regler för att påskynda ett arbetsflöde som har väntat på ett godkännande under en längre tid. Du kan aktivera processen för ändringshantering för alla leverantörer eller för vissa leverantörer. Du kan även ställa in processen så att den kan åsidosättas för enskilda inköpsorder.

När ändringshantering är aktiverad genomgår inköpsorder sex godkännandestatusar, från **Utkast** till **Slutförd**. När en order har godkänts måste användaren som vill ändra den använda åtgärden **Begär ändring**.

| Godkännandestatus | Beskrivning                                                                      | Begär ändring är aktiverad |
|-----------------|----------------------------------------------------------------------------------|---------------------------|
| Utkast           | Inköpsordern är ett utkast och har inte skickats för godkännande i arbetsflödet för inköpsorder.     | Nej                        |
| Undergår granskning       | Inköpsordern har skickats för godkännande i arbetsflödet för inköpsorder. Väntar på godkännande.       | Nej                        |
| Avvisad        | Inköpsordern avvisades under godkännandeprocessen.                                 | Nej                        |
| Godkända        | Inköpsordern har godkänts.                                                             | Ja                       |
| Bekräftat       | Inköpsordern har bekräftats. En inköpsorder kan inte bekräftas förrän den har godkänts.        | Ja                       |
| Slutlig version       | Inköpsordern slutfördes. Den är nu stängd, ur ett ekonomiskt perspektiv, och kan inte längre ändras. | Nej                        |

## <a name="confirming-purchase-orders"></a>Bekräfta inköpsorder
Inköpsorder som har godkännandestatusen **Godkänd** kan genomgår ytterligare steg innan de bekräftas. Du kan exempelvis behöva skicka en förfrågan om inköp till leverantören och fråga om priser, rabatter eller leveransdatum. Du kan då ange statusen på inköpsordern till **Under extern granskning** med hjälp av åtgärden **Inköpsförfrågan**.

Leverantörer som har ställts in för att använda Leverantörsportalen kan granska order via portalen och godkänna eller avvisa dem. Under granskningsprocessen har inköpsordern statusen **Under extern granskning**. Leverantörsportalen kan konfigureras så att en bekräftelse från leverantören automatiskt bekräftar ordern i Supply Chain Management. Du kan även bekräfta en inköpsorder manuellt efter att du har mottagit en bekräftelse från leverantören. Om en leverantör avvisar en inköpsorder kommer avvisandet att åtföljas av orsaken till avvisandet och förslag om ändringar. I det här fallet förblir statusen för inköpsordern **Under extern granskning**.

Det finns även ett alternativ för att generera en proformabekräftelse för en order innan den faktiska bekräftelsen har bearbetats. Det här alternativet skapar enbart en rapport som du kan dela med leverantören. Det skapar ingen journalinformation.

När leverantören har bekräftat ordern är nästa steg att registrera inköpsordern som godkänd. Du kan slutföra det här steget genom att antingen använda åtgärden **Bekräftelse** eller **Bekräfta**. Båda åtgärderna ändrar godkännandestatusen för ordern till **Bekräftad**. Bekräftelse av en order initierar ytterligare två processer:

-   En journal skapas för att spara en exakt kopia av vad som har bekräftats i systemet. Ibland kräver order ändringar och fler journaler skapas efter att den uppdaterade ordern har bekräftats. De här journalerna kan användas för att visa historiken för olika versioner av ordern som har bekräftats.
-   Redovisningsfördelningar skapas och order- och budgetkontroller utförs om den här funktionen har aktiverats. Om någon av kontrollerna misslyckas visas ett felmeddelande om att ändringar måste göras i inköpsordern innan den kan bekräftas igen.

En leverantör kan begära någon form av garanti för att betalningen för ett inköp ska genomföras. Det finns olika metoder för att tillhandahålla denna garanti inom leverantörsreskontraprocesser. Åtgärden **Förskottsbetalning** reserverar medel för inköpsordern och förskottsbetalningen registreras på inköpsordern.

## <a name="changing-purchase-orders"></a>Ändra inköpsorder
I vissa situationer kan du behöva ändra en inköpsorder när den har fått godkännandestatusen **Godkänd** eller **Bekräftad**.

Om inköpsordern skapades med hjälp av en hanteringsprocess kan du utföra ändringar genom att återkalla ordern eller, om ordern redan har godkänts, med hjälp av åtgärden **Begär ändring**. I det här fallet ändras godkännandestatusen tillbaka till **Utkast** och du kan därefter ändra ordern. När du har genomfört ändringarna kan du behöva skicka inköpsordern för godkännande igen. Du kan konfigurera vilka typer av ändringar som kräver ett omgodkännande med hjälp av policyregeln **Regel för omgodkännande av inköpsorder** på sidan **Inköpspolicyer**.

Om en del av den beställda kvantiteten för en inköpsorderrad har levererats kan du inte ändra den beställda kvantiteten när inköpsordern är i **Utkast**. Du kan emellertid ändra kvantiteten **Resterande leverans** på raden för den inköpsorder som har statusen **utkast**.

När en order har bekräftats kan du inte längre ta bort den. Du kan dock ändra den totala kvantiteten eller den resterande kvantiteten för en order under förutsättning att kvantiteten inte har tagits emot eller fakturerats. Du kan sedan använda åtgärden **Slutför** för att förhindra ytterligare bearbetning. 


## <a name="canceling-purchase-orders"></a>Avbryter inköpsorder

En inköpsorder kan avbrytas med hjälp av åtgärden **Avbryt** i huvudet.

Om kvantiteten har delvis registrerats, mottagits eller fakturerats kan du endast annullera den resterande kvantitet som inte har registrerats, tagits emot eller fakturerats. Orderkvantiteten reduceras sedan i enlighet med detta. När kvantiteten på raden uppdateras, uppdateras även radstatus. Den ursprungliga kvantiteten på raden är till exempel 5, och kvantiteten 3 inlevereras. I det här fallet kan endast två avbrytas. Raden uppdateras sedan till **mottagen** status.

Om en leveransrest läggs till på orderraden och den överskrider kvantiteten på orderraden, avbryts inte den överskjutande kvantiteten av åtgärden **Avbryta**. I stället behålls raden i status **öppen order** eftersom den har en resterande kvantitet. Den ursprungliga kvantiteten på raden är till exempel 5, och leveransrest är 7. Om ordern annulleras avbryts kommer fem att avbrytas och kvantiteten 2 finns kvar som du kan se i lagertransaktionerna.

Om du vill avbryta hela kvantiteten på en inköpsorderrad ska du annullera leveransens kvantitet på raden. Raden kommer sedan att uppdateras till **annullerad** status.

Om en inköpsorder är under ändringshantering måste alla ändringar, till exempel annullering av ordern eller leveransresten, skickas till arbetsflödessystemet och godkännas innan det går att slutföra processen och lagertransaktionerna kan uppdateras som annullerade.

<a name="additional-resources"></a>Ytterligare resurser
--------

[Översikt av inköpsorder](purchase-order-overview.md)

[Skapa inköpsorder](purchase-order-creation.md)

[Produktinleverans mot inköpsorder](product-receipt-against-purchase-orders.md)

[Översikt över leverantörsfakturor](../../finance/accounts-payable/vendor-invoices-overview.md)



