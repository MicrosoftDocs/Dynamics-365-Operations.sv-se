---
title: Samarbeta med leverantörer med hjälp av leverantörsportalen
description: Denna artikel beskriver hur inköpsagenter kan använda leverantörsportalen för samarbete med externa leverantörer under bekräftelseprocessen för inköpsorder. Denna information gäller endast Dynamics AX-versionerna från februari 2016 &amp; maj 2016.
author: kamaybac
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchVendorPortalRequests
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9504cd02cc2b9e0495cffc950a0c014d3694dc2a9b74772b8ab0fb40c5a88618
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780564"
---
# <a name="collaborate-with-vendors-by-using-the-vendor-portal"></a>Samarbeta med leverantörer genom leverantörsportalen

[!include [banner](../includes/banner.md)]

Denna artikel beskriver hur inköpsagenter kan använda leverantörsportalen för samarbete med externa leverantörer under bekräftelseprocessen för inköpsorder. Denna information gäller endast Dynamics AX-versionerna från februari 2016 och maj 2016.

Informationen i det här avsnittet gäller bara Dynamics AX-versionerna från februari 2016 och maj 2016. För mer information om det nya leverantörssamarbetet, se [Leverantörssamarbeten med externa leverantörer](vendor-collaboration-work-external-vendors.md).  

Leverantörsportalen vänder sig till leverantörer som inte har elektroniskt datautbyte (EDI) med Microsoft Dynamics AX för utbyte av inköpsorderinformation (IO). Portalen gör att inköpsagenter kan skicka en inköpsorder till leverantören och sedan få ett bekräftat eller avvisat svar direkt i Dynamics AX.  

Processen kan konfigureras så att en bekräftelse från leverantören automatiskt bekräftar ordern. I det här fallet behövs uppföljning bara ibland, när en order avslås eller om säljarens bekräftelse är registrerad som ett svar men statusen för IO:n är inte uppdaterad till **Bekräftad** på grund av ett problem med bekräftelseprocessen.

## <a name="po-confirmation-and-rejection"></a>IO-bekräftelse och -avvisande
Inköpsorder förbereds i Dynamics AX. När du har en IO som har statusen **Godkänd** skickar du den till leverantören genom att generera bekräftelseförfrågan. Om du vill dra säljarens uppmärksamhet till en ny inköpsorder kan du även använda utskriftshanteringssystemet för att skicka IO:n via e-post. Inköpsordern visas på leverantörsportalen med möjlighet för säljaren att bekräfta eller avvisa den. Leverantören kan också lägga till kommentarer för att kommunicera information som ändringar i IO:n.  

På leverantörsportalen kan leverantören se orderrader. Dessa rader innehåller information som det externa produktnumret, dimensioner, prisinformation, kvantitet, leveransdatum och leveransadress. Leverantören kan generera en rapport som visar inköpsorderinformationen och också det totala priset. Avgifter som är relevanta för leverantören visas om leverantören klickar på **Avgifter** på knappen i sidhuvudet eller på raderna. Leverantörer kan importera PO information i sina egna system med **Export till Excel** funktionsduglighet.  

Följande tabell visar det typiska utbytet av information, beroende på hur säljaren svarar när du skickar en IO för bekräftelse.

| Svarstyp                                                                                                  | Resultat                                                                                                                                                                                                                                                                                          |
|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Leverantören bekräftar ordern. Systemet har konfigurerats för att automatiskt bekräfta inköpsorder när leverantören bekräftar.    | Statusen för ordern uppdateras till **Bekräftad**. Om något hindrar ordern från att uppdateras registreras säljarens svar fortfarande som **Bekräftad** men statusen för IO:n förblir **I extern granskning**.                                                                       |
| Leverantören bekräftar ordern. Systemet har inte konfigurerats för att automatiskt bekräfta inköpsorder när leverantören bekräftar. | Säljarens svar registreras som **Bekräftad** men statusen för IO:n förblir **I extern granskning**.                                                                                                                                                                                      |
| Leverantören avvisar ordern.                                                                                     | Säljarens svar registreras som **Avvisad** och statusen för IO:n förblir **I extern granskning**. Avvisandet tas emot tillsammans med orsaken och ett förslag till ändring, till exempel ett alternativt leveransdatum. Du uppdaterar IO:n och skickar sedan en ny version för bekräftelse. |

## <a name="changes-to-a-po"></a>Ändringar i en PO
När du måste ändra en IO som redan bekräftats kan du skicka en ny inköpsorder till leverantören via leverantörsportalen. Den nya IO:n får ett versionssuffix som visar att den är en modifierad version av en IO som meddelades tidigare. Leverantörsportalen låter leverantörer följa historiken för varje order. Föregående bekräftade versionen av IO:n ligger kvar i listan över bekräftade IO:r tills den nya IO:n har bekräftats.  

När du annullerar en IO, statusen ändras till **Godkänd**. Du måste skicka tillbaka IO:n till säljaren via leverantörsportalen så att leverantören kan bekräfta eller avvisa annulleringen. När annulleringen har bekräftats visas IO:n i leverantörens lista över bekräftade IO:r som **Annullerad**.

## <a name="versions-status-transitions-and-change-management"></a>Versioner, statusövergångar och ändringshantering
När en IO skickas till leverantören registreras den i systemet som en specifik version av inköpsordern och statusen ändras från **Godkänd** till **I extern granskning**. Om IO:n ändras senare, en ny version av IO:n skapas och status går tillbaka till **Godkänd** (eller **Utkast** om förändringshantering är aktiverad).  

Tabellen nedan visar ett exempel på förändringar i status och version som en IO kan gå igenom.

| Åtgärd                                                   | Status och version                                                                                    |
|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
| Den första versionen av inköpsordern skapas i Dynamics AX. | Statusen är **Godkänd**.                                                                           |
| IO:n skickas till leverantörsportalen.                     | En version registreras på leverantörsportalen och statusen ändras till **I extern granskning**.    |
| Du gör några förändringar som begärs av leverantören.  | Statusen ändras tillbaka till **Godkänd**.                                                            |
| Du skickar den nya versionen av IO:n till leverantörsportalen. | En version registreras på leverantörsportalen och statusen ändras till **I extern granskning**. |
| Leverantören godkänner den nya versionen av IO:n.           | Tillståndet ändras till **Bekräftad**.                                                                |

För att se de versioner av IO som har skickats till leverantören (och leverantörens svar), klicka på **Journaler** &gt; **Bekräftelsebegäran** i IO.  

Order som skickats till leverantören för en reaktion och har statusen **I extern granskning** visas i antingen listan **Inköpsorder har skickats till leverantörsportalen, väntar på svar** eller listan **Inköpsorder som har skickats till leverantörsportalen, åtgärd krävs för svaret**. När du ändrar en order som skickats till leverantören så att statusen ändras tillbaka till **Godkänd** visas ordern inte längre i dessa listor. Om du vill se om det finns tidigare svar från leverantören angående ordern, klicka på **Journaler** &gt; **Bekräftelsebegäran**.  

Leverantörerna måste inte bekräfta IO:n på leverantörsportalen. De kan också skicka ett e-postmeddelande eller kommunicera deras acceptans av en IO via andra kanaler. Du kan sedan bekräfta ordern manuellt i Dynamics AX. I det här fallet får du en varning om att ordern bekräftas, även om det inte finns något svar från leverantören. IO:n visas sedan i bekräftelsehistoriken i leverantörsportalen som en öppen bekräftad order som inte har några svar. Leverantören har sedan inte längre möjlighet att bekräfta eller avvisa inköpsordern.  

**Obs!** Den version av IO:n som är tillgänglig för andra processer i Dynamics AX är alltid senaste versionen, även om denna version ännu inte registrerats.

### <a name="change-management"></a>Ändringshantering

Om du har inaktiverat förändringshantering för en IO, går IO:n via en godkännandearbetsflöde för att nå statusen **Godkänd**. Denna process är inte synlig för leverantören.  

När förändringshantering aktiveras för en IO, registreras versionen när IO:n godkänns, inte när IO:n skickas till leverantören eller bekräftas.  

Tabellen nedan visar ett exempel på förändringar i statusen och versionen som en IO kan gå igenom när ändringshantering är aktiverad.


|                                                    Åtgärd                                                     |                                                                                                                                                                                                                      Status och version                                                                                                                                                                                                                      |
|---------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                           Den första versionen av inköpsordern skapas i Dynamics AX.                            |                                                                                                                                                                                                            Statusen är <strong>Utkast</strong>.                                                                                                                                                                                                             |
| IO:n är skickad till godkännandeprocessen. (Detta är en intern process som leverantören inte ingår i.) |                                                                                                                        Statusvärdet ändras från <strong>Utkast</strong> till <strong>Under granskning</strong> till <strong>Godkännande</strong> om IO:n inte avvisas under godkännandeprocessen. Den godkända inköpsordern registreras som en version.                                                                                                                        |
|                                      PO skickas till leverantören portal                                      |                                                                                                                                                                      Versionen registreras på leverantörsportalen och statusen ändras till <strong>I extern granskning</strong>.                                                                                                                                                                       |
|                            Du gör några förändringar som begärs av leverantören.                            |                                                                                                                                                                                                    Statusen ändras tillbaka till <strong>Utkast</strong>.                                                                                                                                                                                                     |
|                              IO:n skickas till godkännandeprocessen igen.                               | Statusvärdet ändras från <strong>Utkast</strong> till <strong>Under granskning</strong> till <strong>Godkännande</strong> om IO:n inte avvisas under godkännandeprocessen. Alternativt kan systemet konfigureras så att specifika fältändringar inte kräver nytt godkännande. I det här fallet ändras statusen först till <strong>Utkast</strong> och sedan uppdateras automatiskt till <strong>Godkänd</strong>. Den godkända inköpsordern registreras som en ny version. |
|                           Du skickar den nya versionen av IO:n till leverantörsportalen.                            |                                                                                                                                                                    Den nya versionen registreras på leverantörsportalen och statusen ändras till <strong>I extern granskning</strong>.                                                                                                                                                                     |
|                                Leverantören godkänner den nya versionen av IO:n.                                 |                                                                                                                                                     Statusen ändras till <strong>Bekräftad</strong> antingen automatiskt eller när du får svar från leverantören och sedan bekräftar IO:n.                                                                                                                                                     |

## <a name="additional-resources"></a>Ytterligare resurser

[Användarsäkerhet för leverantörportal](configure-security-vendor-portal-users.md)

[Arbetsyta för leverantörssamarbetesfakturering](../../finance/accounts-payable/vendor-portal-invoicing-workspace.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]