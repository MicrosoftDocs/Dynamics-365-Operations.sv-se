---
title: "Leverantörssamarbete med externa leverantörer"
description: "I det här avsnittet beskrivs hur inköpare kan samarbeta med externa leverantörer för att byta ut information om inköpsorder och försändelselager."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b141ed78306504949eae641377b5c5a2b0599572
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="vendor-collaboration-with-external-vendors"></a>Leverantörssamarbete med externa leverantörer

[!include[banner](../includes/banner.md)]


I det här avsnittet beskrivs hur inköpare kan samarbeta med externa leverantörer för att byta ut information om inköpsorder och försändelselager.

Modulen för **Leverantörssamarbete** vänder sig till leverantörer som inte har elektronisk dataväxling (EDI) med Microsoft Dynamics 365 for Operations. Med den kan leverantörer arbeta med inköpsorder, faktura och information om försändelselager. I det här avsnittet beskrivs hur du kan samarbeta med externa leverantörer som använder gränssnittet för leverantörssamarbete när de arbetar med inköpsorder och försändelselagret. Det beskriver även hur du låter en viss leverantör använda leverantörssamarbeten, samt hur du definierar den information som alla leverantörer ska få se när de svarar på en inköpsorder. För mer information om vad externa leverantörer kan göra i gränssnittet för leverantörssamarbeten, se [Leverantörssamarbete med kunder](vendor-collaboration-work-customers-dynamics-365-operations.md).  

För mer information om hur leverantörer kan använda leverantörssamarbeten i faktureringsprocessen, se [Arbetsyta för leverantörssamarbetesfakturering](/dynamics365/operations/financials/accounts-payable/vendor-portal-invoicing-workspace). För mer information hur du reserverar nya användare av leverantörssamarbeten, se [Hantera användare av leverantörssamarbete](manage-vendor-collaboration-users.md).

## <a name="define-the-information-shown-to-vendors-when-they-respond-to-pos"></a>Definiera den information som visas för leverantörer när dessa svarar på inköpsorder
När leverantörer svarar på en inköpsorder som du skickar till dem, visas en dialogruta där de måste bekräfta att de vill godkänna, avvisa eller godkänna inköpsordern med ändringar. Den information som måste visas för leverantören vid den tidpunkten kan vara specifik för din verksamhet, så du kan ange den text som ska visas i vart och ett av de tre bekräftelsemeddelandena. Texten kan till exempel informera leverantören om de nästkommande stegen i processen, eller om leveransvillkor och villkor.  

Om du vill definiera den text som visas i svaret på inköpsordern:

1.  Öppna sidan **Information för leverantörer som svarar på inköpsordrar**.
2.  Välj en av följande svarstyper:
3.  Klicka på **Redigera**
4.  Ange den information som du vill att leverantörerna ska få se i rutan **Informationsmeddelande**.

Om du behöver lägga till meddelanden på flera språk, skapa då separata meddelanden med lämpliga språkkoder. Leverantören får se meddelandet på det språk som de använder.

## <a name="set-the-vendor-collaboration-options-for-a-specific-vendor"></a>Ange alternativen för leverantörssamarbete för en specifik leverantör
De allmänna inställningarna för leverantörssamarbete i med Dynamics 365 for Operations konfigureras av en administratör. Till exempel avgör dessa vilka säkerhetsroller som är tillgängliga för alla leverantörer som du samarbetar med. Det finns också vissa inställningar som kan skilja sig för respektive leverantörskonto, och du måste ange dessa:

-   Aktivera leverantörssamarbeten.
-   Bestäm om du vill att leverantören ska få se prisinformation.

### <a name="enable-vendor-collaboration"></a>Aktivera leverantörssamarbeten

Innan användarkonton kan skapas för en extern leverantör, måste du konfigurera leverantörskontot om du vill låta dem använda leverantörssamarbeten. För att göra detta, ange fältet **Samarbetesaktivering** som aktivt i fliken **Allmänt** på sidan **Leverantörer**. Det finns två väljare som du kan välja mellan:

-   **Aktiv (IO bekräftas automatiskt)**- Inköpsorder bekräftas automatiskt när leverantören godkänner dem utan ändringar.
-   **Aktiv (IO bekräftas inte automatiskt)**- Inköpsorder måste bekräftas manuellt av din organisation efter det att leverantören har godkänt dem.

### <a name="decide-whether-you-want-the-vendor-to-see-price-information"></a>Bestäm om du vill att leverantören ska få se prisinformation

Om du vill dela information om exempelvis enhetspris, rabatter och avgifter via samarbetsgränssnittet, måste du ange alternativet **Inköpsorderpriser/belopp** som **Ja** på leverantörskontot. Detta alternativt finns i fliken **Standardvärden för inköpsorder**.

## <a name="work-with-pos-when-using-vendor-collaboration"></a>Arbeta med inköpsorder när du använder leverantörssamarbeten
### <a name="sending-a-po-to-the-vendor"></a>Skicka en inköpsorder till leverantören

Inköpsorder skapas i Dynamics 365 for Operations. När inköpsordern har statusen **Godkänd** skickar du den till leverantören med åtgärden **Skicka för bekräftelse** på sidan **Inköpsorder**. Statusen för inköpsordern ändras till i **I extern granskning**. När inköpsordern har skickats, kan leverantören se den på sidan **Inköpsorder för granskning** i gränssnittet för leverantörssamarbete, där de kan godkänna, avvisa eller föreslå ändringar i ordern. Leverantören kan också lägga till kommentarer för att kommunicera information som ändringar i IO:n. Om du vill dra säljarens uppmärksamhet till en ny inköpsorder kan du även använda utskriftshanteringssystemet för att skicka IO:n via e-post.

### <a name="confirmation-and-acceptance-of-the-po-by-the-vendor"></a>Bekräftelse och godkännande av inköpsordern av leverantören

När en leverantör har godkänt en inköpsorder kan den bekräftas automatiskt, eller också kan den komma att behöva bekräftas manuellt. Detta beror på om fältet **Leverantörsaktivering** är inställt på **Aktiv (IO bekräftas automatiskt)** för leverantören, eller på **Aktiv (IO bekräftas inte automatiskt)**.  

Följande tabell visar det typiska informationsutbytet, beroende på hur leverantören svarar när du skickar en inköpsorder för bekräftelse.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Leverantörssvar</strong></td>
<td><strong>Resultat</strong></td>
</tr>
<tr class="even">
<td>Leverantören <strong>godkänner</strong> ordern. Dynamics 365 for Operations har konfigurerats för att automatiskt bekräfta inköpsorder när leverantören godkänner.</td>
<td>Statusen för ordern uppdateras till <strong>Bekräftad</strong>. Om något hindrar ordern från att uppdateras, registreras säljarens svar fortfarande som <strong>Godkänt</strong>, men statusen för inköpsordenr förblir <strong>i extern granskning</strong>.</td>
</tr>
<tr class="odd">
<td>Leverantören <strong>godkänner</strong> ordern. Dynamics 365 for Operations har inte konfigurerats för att automatiskt bekräfta inköpsorder när leverantören godkänner.</td>
<td>Säljarens svar registreras som <strong>Godkänt</strong>, men statusen för inköpsordern förblir <strong>i extern granskning</strong>.</td>
</tr>
<tr class="even">
<td>Leverantören <strong>avvisar</strong> ordern.</td>
<td>Säljarens svar registreras som <strong>Avvisad</strong> och statusen för IO:n förblir <strong>I extern granskning</strong>. Kasseringen tas emot tillsammans med leverantöranmärkningen.</td>
</tr>
<tr class="odd">
<td>Leverantören <strong>accepterar ordern med ändringar</strong>. Ändringar föreslås på radnivån. Det går att godkänna eller avvisa att enskilda rader. Andra föreslagna ändringar inkluderar:
<ul>
<li>Ändra datum eller kvantiteter.</li>
<li>Dela rader för andra leveransdatum eller kvantiteter.</li>
<li>Byta ut en artikel.</li>
</ul>
Prisinformation och avgifter kan inte ändras av leverantören. Förslag till ändringar på dessa kan göras med hjälp av anteckningar.</td>
<td>Säljarens svar registreras som <strong>Godkänd med ändringar</strong>, <strong></strong> och inköpsorderns status förblir <strong>I extern granskning</strong>.</td>
</tr>
</tbody>
</table>

Du kan använda arbetsytan **Förberedelse** **av inköpsorder** för att övervaka vilka inköpsorder som leverantören har svarat på. Den här arbetsytan innehåller två listor med inköpsorder med statusen **I extern granskning**:

-   "I extern granskning" kräver åtgärd.
-   "I extern granskning" inväntar leverantörssvar.

### <a name="changing-a-po"></a>Ändra en inköpsorder

När du behöver ändra en inköpsorder som redan har besvarats, skickar du en ny version av inköpsordern till leverantören. Den nya inköpsordern får ett versionstillägg som visar att den är en modifierad version av en inköpsorder som meddelats tidigare. Sidan **Historik för inköpsorderleverantörsbekräftelse** låter dig och dina leverantörer spåra historiken för respektive order. Föregående bekräftad version av inköpsordern ligger kvar i listan över bekräftade inköpsorder tills den nya inköpsordern har bekräftats.

### <a name="cancelling-a-po"></a>Avbryta en inköpsorder

När du avbryter in inköpsorder ändras statusen till **Approved**. Du måste skicka tillbaka IO:n till säljaren via leverantörsportalen så att leverantören kan bekräfta eller avvisa annulleringen. När annulleringen har bekräftats visas inköpsordern i leverantörens lista över bekräftade inköpsorder som **Annullerat**.

### <a name="adding-attachments-to-a-po"></a>Lägga till bilagor till en inköpsorder

Du kan lägga till bilagor som till exempel filer, bilder och anteckningar till inköpsordern genom att använda dokumenthanteringssystemet. Bilagorna som läggs till med en begränsning av typen **Extern** kommer att vara synliga för leverantören när du skickar inköpsordern till dem.

## <a name="purchase-order-statuses-and-versions"></a>Status och versioner för inköpsorder
I det här avsnittet beskrivs olika statusvärden som en inköpsorder kan ha upp till den tidpunkt då den bekräftas, och vid denna tidpunkt kommer nya versioner av inköpsordern att göras tillgängliga för leverantören. Det finns skillnader i detta, beroende på om du använder ändringshantering för inköpsorder. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Versioner och status om du inte använder ändringshantering

Tabellen nedan visar ett exempel på förändringar i status och version som en IO kan gå igenom.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Åtgärd**                                                               | **Status och version**                                                                                                                                       |
| Den första versionen av inköpsordern skapas i Dynamics 365 for Operations. | Statusen är **Godkänd**.                                                                                                                                  |
| Inköpsordern skickas till leverantören.                                            | En version registreras i gränssnittet för leverantörssamarbete, och statusen ändras till **I extern granskning**.                                          |
| Leverantören skickar svaret **Godkänd med ändringar**.                  | Statusvärdet är fortfarande **I extern granskning**.                                                                                                                  |
| Du gör några förändringar som begärs av leverantören.                  | Statusen ändras till **Approved**.                                                                                                                        |
| Du skickar den nya versionen av inköpsordern till leverantören.                        | En ny version registreras i gränssnittet för leverantörssamarbete, och statusen ändras till **I extern granskning**.                                      |
| Leverantören godkänner den nya versionen av inköpsordern.                            | Statusvärdet är fortfarande **I extern granskning** såvida inte leverantörskontot har konfigurerats att automatiskt ange inköpsordern till statusen **Bekräftat** när de godkänner den. |

Leverantörer måste inte bekräfta inköpsordern i gränssnittet för leverantörssamarbete. De kan också skicka ett e-postmeddelande eller kommunicera deras acceptans av en IO via andra kanaler. Du kan sedan bekräfta ordern manuellt i Dynamics 365 for Operations. Om du gör detta får du en varning om att ordern bekräftas, även om det inte finns något svar från leverantören. Inköpsordern visas sedan i bekräftelsehistoriken som en öppen, bekräftad order som inte har fått några svar. Leverantören har inte längre möjlighet att bekräfta eller avvisa inköpsordern.  

**Obs!** Den version av inköpsordern som är tillgänglig för andra processer i Dynamics 365 for Operations är alltid den senaste versionen, även om denna version ännu inte har registrerats i gränssnittet för leverantörssamarbete.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Versioner och status om du använder ändringshantering

Om du har inaktiverat ändringshantering för inköpsorder, kommer inköpsordern att genomgå ett arbetsflöde för godkännande för att nå statusen **Godkänd**. Denna process är inte synlig för leverantören.  

Tabellen nedan visar ett exempel på förändringar i statusen och versionen som en IO kan gå igenom när ändringshantering är aktiverad. Versionen registreras när inköpsordern godkänns, inte när inköpsordern skickas till leverantören eller bekräftas.

|                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Åtgärd**                                                                                                    | **Status och version**                                                                                                                                                                                                                                                                                                                                                                      |
| Den första versionen av inköpsordern skapas i Dynamics 365 for Operations.                                      | Statusen är **Utkast**.                                                                                                                                                                                                                                                                                                                                                                    |
| IO:n är skickad till godkännandeprocessen. (Detta är en intern process som leverantören inte är inblandad i.) | Statusen ändras från **Draft** till **In Review** till **Approval** om inköpsordern inte avvisas i samband med godkännandeprocessen. Den godkända inköpsordern registreras som en version.                                                                                                                                                                                                                     |
| Inköpsordern skickas till leverantören                                                                                  | Versionen registreras i gränssnittet för leverantörssamarbete, och statusen ändras till **I extern granskning**.                                                                                                                                                                                                                                                                       |
| Du gör några förändringar som begärs av leverantören.                                                       | Statusen ändras tillbaka till **Utkast**.                                                                                                                                                                                                                                                                                                                                                    |
| IO:n skickas till godkännandeprocessen igen.                                                            | Statusen ändras från **Draft** till **In Review** till **Approval** om inköpsordern inte avvisas under godkännandeprocessen. Alternativt kan systemet konfigureras så att specifika fältändringar inte kräver nytt godkännande. I det här fallet ändras statusen först till **Utkast** och sedan uppdateras automatiskt till **Godkänd**. Den godkända inköpsordern registreras som en ny version. |
| Du skickar den nya versionen av inköpsordern till leverantören.                                                             | Den nya versionen registreras i gränssnittet för leverantörssamarbete, och statusen ändras till **I extern granskning**.                                                                                                                                                                                                                                                                   |
| Leverantören godkänner den nya versionen av IO:n.                                                                | Statusen ändras till **Bekräftad** antingen automatiskt eller när du får svar från leverantören och sedan bekräftar IO:n.                                                                                                                                                                                                                                                     |

## <a name="share-information-about-consignment-inventory"></a>Dela information om försändelselager
Om du använder försändelselager, kan leverantörerna använda gränssnittet för leverantörssamarbete för att visa information på följande sidor:

-   **Inköpsorder som förbrukar försändelselager** - Inköpsorder för försändelselager skapas när ägarskapet för lagret ändras från leverantören till ditt företag. En produktinleverans bokförs samtidigt. Dessa försändelseinköpsorder visas bara på sidan **Inköpsorder som förbrukar försändelselager**. De inkluderas inte på sidan **Alla bekräftade inköpsorder** i modulen **Leverantörssamarbete**.
-   **Mottagna produkter från försändelselager** - Den här sidan visar alla transaktioner där ägarskapet för produkter har överförts från leverantören till ditt företag. Leverantörer kan använda den här informationen för att fakturera kunden.
-   **Behållning i försändelselager** - Den här sidan visar det leverantörsägda, tillgängliga försändelselagret som har inlevererats på ditt lagerställe.





