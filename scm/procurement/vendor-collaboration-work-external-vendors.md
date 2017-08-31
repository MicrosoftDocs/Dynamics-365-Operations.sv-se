---
title: "Leverantörssamarbete med externa leverantörer"
description: "I det här avsnittet beskrivs hur inköpare kan samarbeta med externa leverantörer för att byta ut information om inköpsorder och försändelselager."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: cbd099403f48b502ca74bcb38ae12decedb8f2da
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---

# <a name="vendor-collaboration-with-external-vendors"></a>Leverantörssamarbete med externa leverantörer

[!include[banner](../includes/banner.md)]


I det här avsnittet beskrivs hur inköpare kan samarbeta med externa leverantörer för att byta ut information om inköpsorder och försändelselager.

Modulen **Leverantörssamarbete** vänder sig till leverantörer som inte har elektronisk dataväxling (EDI) med Microsoft Dynamics 365 for Finance and Operations. Med den kan leverantörer arbeta med inköpsorder, faktura och information om försändelselager. I det här avsnittet beskrivs hur du kan samarbeta med externa leverantörer som använder gränssnittet för leverantörssamarbete när de arbetar med inköpsorder och försändelselagret. Det beskriver även hur du låter en viss leverantör använda leverantörssamarbeten, samt hur du definierar den information som alla leverantörer ska få se när de svarar på en inköpsorder. För mer information om vad externa leverantörer kan göra i gränssnittet för leverantörssamarbeten, se [Leverantörssamarbete med kunder](vendor-collaboration-work-customers-dynamics-365-operations.md).  

För mer information om hur leverantörer kan använda leverantörssamarbeten i faktureringsprocessen, se [Arbetsyta för leverantörssamarbetesfakturering](/dynamics365/unified-operations/financials/accounts-payable/vendor-portal-invoicing-workspace). För mer information hur du reserverar nya användare av leverantörssamarbeten, se [Hantera användare av leverantörssamarbete](manage-vendor-collaboration-users.md).

För mer information om hur leverantörer kan använda leverantörssamarbeten i faktureringsprocessen, se [Arbetsyta för leverantörssamarbetesfakturering](/dynamics365/unified-operations/financials/accounts-payable/vendor-portal-invoicing-workspace). 

För mer information hur du reserverar nya användare av leverantörssamarbeten, se [Hantera användare av leverantörssamarbete](manage-vendor-collaboration-users.md).

## <a name="define-the-information-that-is-shown-to-vendors-when-they-respond-to-pos"></a>Definiera information som visas för leverantörer när dessa svarar på inköpsorder
När leverantörer svarar på en inköpsorder som du skickar till dem, visas en meddelanderuta där de måste bekräfta att de vill acceptera, avvisa eller godkänna inköpsordern med ändringar. Eftersom informationen som måste visas för leverantören vid den tidpunkten kan vara specifik för din verksamhet kan du ange den text som ska visas i vart och ett av de tre bekräftelsemeddelandena. Texten kan till exempel informera leverantören om de nästkommande stegen i processen, eller om leveransvillkor och villkor.  

Om du vill definiera den text som visas i svaret på inköpsordern:

1.  Öppna sidan **Information för leverantörer som svarar på inköpsordrar**.
2.  Välj en av följande svarstyper:
3.  Klicka på **Redigera**.
4.  Ange den information som du vill att leverantörerna ska få se i rutan **Informationsmeddelande**.

Om du måste lägga till meddelanden på flera språk, skapa då separata meddelanden och ange lämplig språkkod för varje språk. Meddelandet som visas för leverantören är på det språk leverantören använder.

## <a name="set-the-vendor-collaboration-options-for-a-specific-vendor"></a>Ange alternativen för leverantörssamarbete för en specifik leverantör
De allmänna inställningarna för leverantörssamarbete i Finance and Operation konfigureras av en administratör. Exempelvis avgör en administratör vilka säkerhetsroller som är tillgängliga för de leverantörer du samarbetar med. Även inställningar kan skilja sig åt mellan olika leverantörskonton, och du måste ställa in dessa:
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

Inköpsorder skapas i Finance and Operation. När inköpsordern har statusen **Godkänd** skickar du den till leverantören med hjälp av åtgärden **Skicka för bekräftelse** på sidan **Inköpsorder**. Statusen för inköpsordern ändras till i **I extern granskning**. När inköpsordern har skickats kan leverantören se den på sidan **Inköpsorder för granskning** i gränssnittet leverantörssamarbete. Leverantören kan sedan acceptera eller avvisa ordern eller föreslå ändringar. Leverantören kan också lägga till kommentarer för att kommunicera information som ändringar i IO:n. Om du vill dra säljarens uppmärksamhet till en ny inköpsorder kan du även använda utskriftshanteringssystemet för att skicka IO:n via e-post.

### <a name="confirmation-and-acceptance-of-the-po-by-the-vendor"></a>Bekräftelse och godkännande av inköpsordern av leverantören

När en leverantör har godkänt en inköpsorder kan den bekräftas automatiskt, eller också kan den komma att behöva bekräftas manuellt. Detta beror på om fältet **Leverantörsaktivering** är inställt på **Aktiv (IO bekräftas automatiskt)** eller på **Aktiv (IO bekräftas inte automatiskt)** för leverantören.  

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
<td>Leverantören <strong>godkänner</strong> ordern. Finance and Operations har konfigurerats för att automatiskt bekräfta en inköpsorder när leverantören accepterar den.</td>

<td>Statusen för ordern uppdateras till <strong>Bekräftad</strong>. Om något hindrar ordern från att uppdateras, registreras säljarens svar fortfarande som <strong>Godkänt</strong>, men statusen för inköpsordenr förblir <strong>i extern granskning</strong>. 

Inköpsordern som skickades till leverantören och har statusen **I extern granskning** uppdateras med bekräftat leveransdatum på raderna. Uppdateringen som initierar en ny version uppdateras automatiskt till statusen **Bekräftad**. När inköpsordern har bekräftats visas den i gränssnittet leverantörssamarbete.</td>
</tr>
<tr class="odd">
<td>Leverantören <strong>godkänner</strong> ordern. Finance and Operations har inte konfigurerats för att automatiskt bekräfta en inköpsorder när leverantören accepterar den.</td>
<td>Säljarens svar registreras som <strong>Godkänt</strong>, men statusen för inköpsordern förblir <strong>i extern granskning</strong>.

Inköpsordern som skickades till leverantören och har statusen **I extern granskning** uppdateras med bekräftat leveransdatum på raderna. Uppdateringen initierar en ny version som sätts till **I extern granskning**. Du kommer sedan att kunna bekräfta inköpsordern manuellt.</td>

</tr>
<tr class="even">
<td>Leverantören <strong>avvisar</strong> ordern.</td>
<td>Säljarens svar registreras som <strong>Avvisad</strong> och statusen för IO:n förblir <strong>I extern granskning</strong>. Avvisningen tas emot tillsammans med leverantöranmärkningen.</td>
</tr>
<tr class="odd">
<td>Leverantören <strong>accepterar ordern med ändringar</strong>. Ändringar föreslås på radnivån. Det går att godkänna eller avvisa att enskilda rader. Andra föreslagna ändringar inkluderar:
<ul>
<li>Ändra datum eller kvantiteter.</li>
<li>Dela rader för andra leveransdatum eller kvantiteter.</li>
<li>Byta ut en artikel.</li>
</ul>
Prisinformation och avgifter kan inte ändras av leverantören. Förslag till ändringar på dessa kan göras med hjälp av anteckningar.</td>
<td>Leverantörens svar registreras som <strong>Accepterad med ändringar</strong> och inköpsorderns status förblir <strong>I extern granskning</strong>. Statusen visar vilka typer av ändringar leverantören har föreslagit. Information om automatisk förbrukning av ändringarna finns i avsnittet nedan om hur du uppdaterar inköpsordern när en leverantör föreslår ändringar. </td>
</tr>
</tbody>
</table>

Du kan använda arbetsytan **Förberedelse** **av inköpsorder** för att övervaka vilka inköpsorder som leverantören har svarat på. Den här arbetsytan innehåller två listor med inköpsorder med statusen **I extern granskning**:

-   "I extern granskning" kräver åtgärd.
-   "I extern granskning" inväntar leverantörssvar.

### <a name="changing-a-po"></a>Ändra en inköpsorder

När du behöver ändra en inköpsorder som redan har besvarats måste du skicka en ny version av inköpsordern till leverantören. Den nya inköpsordern får ett versionstillägg som visar att den är en modifierad version av en inköpsorder som meddelats tidigare. Med hjälp av sidan **Historik för leverantörsbekräftelse av inköpsorder** kan du och dina leverantörer spåra historiken för respektive order. Föregående bekräftad version av inköpsordern ligger kvar i listan över bekräftade inköpsorder tills den nya inköpsordern har bekräftats.

### <a name="cancelling-a-po"></a>Avbryta en inköpsorder

När du avbryter in inköpsorder ändras statusen till **Approved**. Du måste skicka tillbaka IO:n till säljaren via leverantörsportalen så att leverantören kan bekräfta eller avvisa annulleringen. När annulleringen har bekräftats visas inköpsordern i leverantörens lista över bekräftade inköpsorder som **Annullerat**.

### <a name="adding-attachments-to-a-po"></a>Lägga till bilagor till en inköpsorder

Du kan lägga till bilagor såsom filer, bilder och anteckningar till inköpsordern genom att använda dokumenthanteringssystemet. Bilagor av typen **Extern** kommer att vara synliga för leverantören när du skickar inköpsordern.

## <a name="update-the-po-when-a-vendor-suggests-changes"></a>Uppdatera inköpsordern när en leverantör föreslår ändringar
Om en leverantör har svarat på inköpsordern och föreslår ändringar är nästa steg att behandla svaret.
**Förberedelse av inköpsorder** i ”I extern granskning” kräver en åtgärdslista. Du kan identifiera en inköpsorder som en leverantör har svarat på som accepterad med ändringar. ”I extern granskning” kräver en åtgärdslista. Du kan även navigera till leverantörens svar. Efter svar kan en leverantör ändra följande information i rubriken.
 
-   Referens för leverantörsdokument
-   Leveranssätt
-   Leveransvillkor
-   Bekräftat leveransdatum

Leverantören kan också lägga till en anteckning eller bifogad fil

På raderna kan leverantören ändra kvantiteten och leveransdatumet, lägga till anteckningar och bilagor, avvisa en rad, ersätta en rad med en annan produkt som ska matas in i som text och dela upp en rad i flera leveranser. Beroende på vilka ändringar som föreslås av leverantören har radstatusen med olika radstatusar:
    
-   **Accepterad med ändringar**
-   **Avvisad**
-   **Ersatt** i det här fallet läggs en extra rad till som har statusen **Ersättning**.
-   **Bekräftad** Dela upp i tidsplan. I det här fallet läggs extra rader med statusen **Schemalägg rader** till.

Om en rad inte har några ändringar är radstatusen **Accepterad**.

Du utläsa tidigare nämnda radstatusar, som anger vilken typ av ändringar som gjorts av leverantören, av svaret. Dessutom kan alla ändrade fält visas i fet stil, vilket hjälper dig att identifiera ändringarna.

Du kan uppdatera en inköpsorder genom att klicka på åtgärden **Behandla uppdatering av inköpsorder** när du har fått svar eller på en rad i taget. Med hjälp av indikatorn **Är uppdateringen av inköpsorder behandlad?** i rubriken och på raderna kan du se om systemet har behandlat rubriker eller rader för att uppdatera inköpsordern med de eventuella ändringar som kommer från svaret. Du kan enbart köra processen **Behandla uppdatering av inköpsorder** en gång per rubrik eller rad.

Inte alla föreslagna ändringar kan uppdateras på en inköpsorder. Endast uppdateringar av rubriken och uppdateringar av datum och kvantiteter på raderna kan uppdateras automatiskt på inköpsordern. För andra ändringar måste du manuellt uppdatera inköpsordern. I detta fall visar indikatorn **Är uppdateringen av inköpsordern behandlad?** **Manuell uppdatering**. Ett exempel på en ändring som måste hanteras manuellt är när en leverantör föreslår en uppdelning av en rad till en tidsplan.

En rad som har statusen **Accepterad** har ett bekräftat leveransdatum som ska uppdateras på inköpsordern när du kör **Behandla uppdatering av inköpsorder**. Anteckningar och bifogade filer överföras inte automatiskt till den aktuella inköpsordern. När du uppdaterar den aktuella inköpsordern via åtgärden **Behandla uppdatering av inköpsorder** kommer handelsavtal inte att utvärderas på inköpsorderraderna.


## <a name="po-statuses-and-versions"></a>Statusar och versioner för inköpsorder
Det här avsnittet beskrivs olika statusvärden som en inköpsorder kan ha tills den har bekräftats. Här beskrivs också vid vilken tidpunkt nya versioner av inköpsordern görs tillgängliga för leverantören. Beteendet varierar beroende på om du använder ändringshantering för inköpsorder. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Versioner och status om du inte använder ändringshantering

Tabellen nedan visar ett exempel på förändringar i status och version som en IO kan gå igenom.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Åtgärd**                                                               | **Status och version**                                                                                                                                       |
| Den första versionen av inköpsordern skapas i Finance and Operations. | Statusen är **Godkänd**.                                                                                                                                  |
| Inköpsordern skickas till leverantören.                                            | En version registreras i gränssnittet för leverantörssamarbete, och statusen ändras till **I extern granskning**.                                          |
| Leverantören skickar svaret **Godkänd med ändringar**.                  | Statusvärdet är fortfarande **I extern granskning**.                                                                                                                  |
| Du gör några förändringar som begärs av leverantören.                  | Statusen ändras till **Approved**.                                                                                                                        |
| Du skickar den nya versionen av inköpsordern till leverantören.                        | En ny version registreras i gränssnittet för leverantörssamarbete, och statusen ändras till **I extern granskning**.                                      |
| Leverantören godkänner den nya versionen av inköpsordern.                            | Statusvärdet är fortfarande **I extern granskning** såvida inte leverantörskontot har konfigurerats att automatiskt ange inköpsordern till statusen **Bekräftat** när de godkänner den. |


Leverantörer måste inte bekräfta inköpsordern med hjälp av gränssnittet leverantörssamarbete. De kan också skicka ett e-postmeddelande eller kommunicera deras acceptans av en IO via andra kanaler. Du kan sedan bekräfta ordern manuellt i Finance and Operations. I det här fallet får du en varning om att ordern bekräftas, även om det inte finns något svar från leverantören. Inköpsordern visas sedan i bekräftelsehistoriken som en öppen, bekräftad order som inte har fått några svar. Leverantören har inte längre möjlighet att bekräfta eller avvisa inköpsordern.  


>[!NOTE]
>Den version av inköpsordern som är tillgänglig för andra processer i Dynamics 365 for Finance and Operations är alltid den senaste versionen, även om denna version ännu inte har registrerats i gränssnittet leverantörssamarbete.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Versioner och status om du använder ändringshantering

Om du har inaktiverat ändringshantering för inköpsorder, kommer inköpsordern att genomgå ett arbetsflöde för godkännande för att nå statusen **Godkänd**. Denna process är inte synlig för leverantören.  

Tabellen nedan visar ett exempel på förändringar i statusen och versionen som en IO kan gå igenom när ändringshantering är aktiverad. Versionen registreras när inköpsordern godkänns, inte när inköpsordern skickas till leverantören eller bekräftas.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Åtgärd**                                                               | **Status och version**                                                                                                                                       |
| Den första versionen av inköpsordern skapas i Finance and Operations.      | Statusen är **Utkast**.  |
| IO:n är skickad till godkännandeprocessen. (Godkännandeprocessen är en intern process som leverantören inte är inblandad i.)                                                           | Statusen ändras från **Draft** till **In Review** till **Approval** om inköpsordern inte avvisas i samband med godkännandeprocessen. Den godkända inköpsordern registreras som en version.           | 
| Inköpsordern skickas till leverantören                                                            | Versionen registreras i gränssnittet för leverantörssamarbete, och statusen ändras till **I extern granskning**.      |
| Du kan göra några ändringar som begärts av leverantören, antingen manuellt eller genom att använda åtgärden på svaret för att uppdatera inköpsordern.                                                            | Statusen ändras tillbaka till **Utkast**.     |
|IO:n skickas till godkännandeprocessen igen.                                                |  Statusen ändras från **Draft** till **In Review** till **Approval** om inköpsordern inte avvisas under godkännandeprocessen. Alternativt kan systemet konfigureras så att specifika fältändringar inte kräver nytt godkännande. I det här fallet ändras statusen först till **Utkast** och sedan uppdateras automatiskt till **Godkänd**. Den godkända inköpsordern registreras som en ny version.                                         |
|Du skickar den nya versionen av inköpsordern till leverantören.                                                |  Den nya versionen registreras i gränssnittet för leverantörssamarbete, och statusen ändras till **I extern granskning**.                                         |
|Leverantören godkänner den nya versionen av IO:n.                                                |  Statusen ändras till **Bekräftad** antingen automatiskt eller när du får svar från leverantören och sedan bekräftar IO:n. |

## <a name="share-information-about-consignment-inventory"></a>Dela information om försändelselager
Om du använder försändelselager, kan leverantörerna använda gränssnittet för leverantörssamarbete för att visa information på följande sidor:

-   **Inköpsorder som förbrukar försändelselager** - Inköpsorder för försändelselager skapas när ägarskapet för lagret ändras från leverantören till ditt företag. En produktinleverans bokförs samtidigt. Dessa försändelseinköpsorder visas bara på sidan **Inköpsorder som förbrukar försändelselager**. De inkluderas inte på sidan **Alla bekräftade inköpsorder** i modulen **Leverantörssamarbete**.
-   **Mottagna produkter från försändelselager** - Den här sidan visar alla transaktioner där ägarskapet för produkter har överförts från leverantören till ditt företag. Leverantörer kan använda den här informationen för att fakturera kunden.
-   **Behållning i försändelselager** - Den här sidan visar det leverantörsägda, tillgängliga försändelselagret som har inlevererats på ditt lagerställe.





