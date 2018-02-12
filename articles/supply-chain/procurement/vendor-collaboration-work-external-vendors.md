---
title: "Leverantörssamarbete med externa leverantörer"
description: "I det här avsnittet förklaras hur inköpare kan samarbeta med externa leverantörer för att byta ut information om inköpsorder och försändelselager."
author: mkirknel
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchRFQCaseTableListPage, VendVendorPortalInvoicePart
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 0ca19ab9ed7a52328c5dd5252c418bb9343bdc2b
ms.openlocfilehash: b56cf58f78e5b3ed9bdd0d88f85d31123ec63451
ms.contentlocale: sv-se
ms.lasthandoff: 12/14/2017

---

# <a name="vendor-collaboration-with-external-vendors"></a>Leverantörssamarbete med externa leverantörer

[!include[banner](../includes/banner.md)]

Modulen **Leverantörssamarbete** vänder sig till leverantörer som inte har elektronisk dataväxling (EDI) med Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Här kan leverantörer arbeta med inköpsorder, fakturor, information för försändelselager och anbudsförfrågningar och även få tillgång till delar av sina huvuddata. I det här avsnittet förklaras hur du kan samarbeta med externa leverantörer som använder gränssnittet för leverantörssamarbete när de arbetar med inköpsorder, anbudsförfrågningar och försändelselager. Det förklaras även hur du låter en viss leverantör använda leverantörssamarbeten, samt hur du definierar den information som alla leverantörer ser när de svarar på en inköpsorder.

För mer information om vad externa leverantörer kan göra i gränssnittet för leverantörssamarbeten, se [Leverantörssamarbete med kunder](vendor-collaboration-work-customers-dynamics-365-operations.md).

> [!NOTE]
> Informationen i det här avsnittet om samarbete för leverantör gäller bara för den aktuella versionen av Finance and Operations. I Microsoft Dynamics AX 7.0 (februari 2016) och Microsoft Dynamics AX programversion 7.0.1 (maj 2016) kan du samarbeta med leverantörer med hjälp av modulen **Leverantörsportal**. För information om modulen **Leverantörsportal**, se [Samarbeta med leverantörer genom leverantörsportalen](collaborate-vendors-vendor-portal.md).

För mer information om hur leverantörer kan använda leverantörssamarbeten i faktureringsprocessen, se [Arbetsyta för leverantörssamarbetesfakturering](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md). För mer information hur du reserverar nya användare av leverantörssamarbeten, se [Hantera användare av leverantörssamarbete](manage-vendor-collaboration-users.md).

## <a name="defining-the-information-that-is-shown-to-vendors-when-they-respond-to-pos"></a>Definiera information som visas för leverantörer när dessa svarar på inköpsorder

När leverantörer svarar på en inköpsorder som du skickar till dem, visas en av tre meddelanderutor där de måste bekräfta att de vill acceptera, avvisa eller godkänna inköpsordern med ändringar. Eftersom informationen som måste visas för leverantören vid den tidpunkten kan vara specifik för din verksamhet kan du ange den text som ska visas i vart och ett av bekräftelsemeddelandena. Texten kan till exempel informera leverantören om de nästkommande stegen i processen, eller om leveransvillkor och villkor.

Så här definierar du den text som visas i svaret på inköpsordern:

1. Gå till sidan **Information för leverantörer som svarar på inköpsordrar**, välj svarstyp och sedan **Redigera**.
2. I rutan **Informationsmeddelande** anger du informationen som ska visas för leverantörer i meddelanderutan.

Om du måste lägga till meddelanden på flera språk, skapa då separata meddelanden och ange lämplig språkkod för varje språk. Meddelandet som visas för varje leverantör är på det språk leverantören använder.

## <a name="setting-the-vendor-collaboration-options-for-a-specific-vendor"></a>Ange alternativen för leverantörssamarbete för en specifik leverantör

En administratör konfigurerar de allmänna inställningarna för leverantörssamarbete i Finance and Operations, till exempel vilka säkerhetsroller som är tillgängliga för alla leverantörer som du samarbetar med. Det finns dock inställningar som kan skilja sig åt mellan olika leverantörskonton. Du bör konfigurera dessa inställningar.

- Aktivera leverantörssamarbeten.
- Ange om leverantören ska se prisinformation.

### <a name="enabling-vendor-collaboration"></a>Aktivera leverantörssamarbeten

Innan användarkonton kan skapas för en extern leverantör, måste du konfigurera leverantörskontot så att leverantören kan använda leverantörssamarbete. Gå till sidan **Leverantörer** och ange fältet **Samarbetesaktivering** på fliken **Allmänt**. Följande alternativ är tillgängliga:

- **Aktiv (IO bekräftas automatiskt)** – Inköpsorder bekräftas automatiskt om leverantören godkänner dem utan ändringar.
- **Aktiv (IO bekräftas inte automatiskt)** – Din organisation måste manuellt bekräfta inköpsorder det att leverantören har godkänt dem.

### <a name="specifying-whether-the-vendor-should-see-price-information"></a>Ange om leverantören ska se prisinformation

Om du vill dela prisinformation för inköpsorder via gränssnittet för leverantörssamarbete måste du ange alternativet **Inköpsorderpriser/belopp** på fliken **Standardvärden för inköpsorder** för leverantörskontot till **Ja**. Prisinformationen omfattar enhetspris, rabatter och avgifter.

## <a name="working-with-pos-when-vendor-collaboration-is-used"></a>Arbeta med inköpsorder när leverantörssamarbete används

### <a name="sending-a-po-to-a-vendor"></a>Skicka en inköpsorder till en leverantör

Inköpsorder förbereds i Finance and Operations. När en inköpsorder har statusen **Godkänd** skickar du den till leverantören genom att välja **Skicka för bekräftelse** på sidan **Inköpsorder**. Statusen för inköpsordern ändras sedan till **I extern granskning**. När inköpsordern har skickats kan leverantören se den på sidan **Inköpsorder för granskning** i gränssnittet leverantörssamarbete. Leverantören kan sedan acceptera eller avvisa inköpsordern eller föreslå ändringar. Leverantören kan också lägga till kommentarer för att kommunicera information som ändringar i IO:n. Om du vill dra säljarens uppmärksamhet till en ny inköpsorder kan du även använda utskriftshanteringssystemet för att skicka inköpsordern via e-post.

### <a name="confirmation-and-acceptance-of-a-po-by-a-vendor"></a>Bekräftelse och godkännande av en inköpsorder av en leverantör

När en leverantör godkänner en inköpsorder kan den bekräftas automatiskt, eller så kanske den måste bekräftas manuellt. Detta beror på om fältet **Samarbetesaktivering** är inställt på **Aktiv (IO bekräftas automatiskt)** eller på **Aktiv (IO bekräftas inte automatiskt)** för leverantören.

Följande tabell visar det typiska informationsutbytet, beroende på leverantörens svar när du skickar en inköpsorder för bekräftelse.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr>
<th>Leverantörssvar</th>
<th>Resultat</th>
</tr>
</thead>
<tbody>
<tr class="even">
<td>Leverantören <strong>godkänner</strong> ordern och Finance and Operations är konfigurerat för att automatiskt bekräfta inköpsorder som leverantören godkänner.</td>
<td>Statusen för ordern uppdateras till <strong>Bekräftad</strong>. Om ordern av någon anledning inte kan uppdateras, registreras leverantörens svar fortfarande som <strong>Godkänd</strong>, men statusen för inköpsordern förblir <strong>I extern granskning</strong>. 

Inköpsordern som skickades till leverantören och har statusen <strong>I extern granskning</strong> uppdateras med bekräftat leveransdatum på raderna. Uppdateringen som initierar en ny version anges automatiskt till statusen <strong>Bekräftad</strong>. När inköpsordern har bekräftats visas den i gränssnittet leverantörssamarbete.</td>
</tr>
<tr class="odd">
<td>Leverantören <strong>godkänner</strong> ordern men Finance and Operations är inte konfigurerat för att automatiskt bekräfta inköpsorder som leverantören godkänner.</td>
<td>Säljarens svar registreras som <strong>Godkänt</strong>, men statusen för inköpsordern förblir <strong>i extern granskning</strong>.

Inköpsordern som skickades till leverantören och har statusen <strong>I extern granskning</strong> uppdateras med bekräftat leveransdatum på raderna. Uppdateringen som initierar en ny version anges automatiskt till statusen <strong>I extern granskning</strong>. Du kan manuellt bekräfta inköpsordern.</td>
</tr>
<tr class="even">
<td>Leverantören <strong>avvisar</strong> ordern.</td>
<td>Säljarens svar registreras som <strong>Avvisad</strong> och statusen för IO:n förblir <strong>I extern granskning</strong>. Avvisningen tas emot tillsammans med leverantöranmärkningen.</td>
</tr>
<tr class="odd">
<td>Leverantören <strong>godkänner</strong> ordern <strong>med ändringar</strong>. Ändringar föreslås på radnivån. Leverantören kan godkänna eller avvisa enskilda rader. Nedan följer några ändringar som leverantören kan föreslå:
<ul>
<li>Ändra datum eller kvantiteter.</li>
<li>Dela rader för andra leveransdatum eller kvantiteter.</li>
<li>Byt ut en artikel.</li>
</ul>
Leverantören kan inte ändra prisinformation och avgifter. Leverantören kan föreslå dessa ändringar med hjälp av anteckningar.</td>
<td>Leverantörens svar registreras som <strong>Accepterad med ändringar</strong> och inköpsorderns status förblir <strong>I extern granskning</strong>. Statusen visar vilka typer av ändringar som leverantören har föreslagit. Information om automatisk förbrukning av ändringarna finns "Uppdatera inköpsordern när en leverantör föreslår ändringar" senare i det här avsnittet. </td>
</tr>
</tbody>
</table>

Du kan använda arbetsytan **Förberedelse av inköpsorder** för att övervaka vilka inköpsorder som leverantören har svarat på. Den här arbetsytan innehåller två listor med inköpsorder med statusen **I extern granskning**:

- I extern granskning kräver åtgärd
- En extern granskning som avvaktar leverantörens svar

### <a name="changing-a-po"></a>Ändra en inköpsorder

När du behöver ändra en inköpsorder som leverantören redan har besvarats måste du skicka en ny version av inköpsordern till leverantören. Den nya inköpsordern får ett versionstillägg som visar att den är en modifierad version av en inköpsorder som skickats tidigare. Med hjälp av sidan **Historik för leverantörsbekräftelse av inköpsorder** kan du och dina leverantörer spåra historiken för respektive order. Föregående bekräftad version av inköpsordern ligger kvar i listan över bekräftade inköpsorder tills den nya inköpsordern har bekräftats.

### <a name="canceling-a-po"></a>Avbryta en inköpsorder

När du avbryter in inköpsorder ändras statusen till **Approved**. Du måste skicka tillbaka inköpsordern till leverantören så att denne kan bekräfta eller avvisa upphävandet. När annulleringen har bekräftats visas IO:n i leverantörens lista över bekräftade IO:r som **Annullerad**.

### <a name="adding-attachments-to-a-po"></a>Lägga till bilagor till en inköpsorder

Du kan lägga till bilagor såsom filer, bilder och anteckningar till inköpsordern genom att använda dokumenthanteringssystemet. Bilagor av typen **Extern** kommer att vara synliga för leverantören när du skickar inköpsordern.

## <a name="updating-a-po-when-a-vendor-suggests-changes"></a>Uppdatera en inköpsorder när en leverantör föreslår ändringar

Om en leverantör har svarat på en inköpsorder och föreslår ändringar är nästa steg att behandla svaret.

I arbetsytan **Förberedelse av inköpsorder** i listan **I extern granskning** kan du identifiera inköpsorder som en leverantör har godkänt med ändringar. Från den här listan kan du navigera till leverantörens svar.

I ett svar kan en leverantör ändra följande information i huvudet.
 
- Referens för leverantörsdokument
- Leveranssätt
- Leveransvillkor
- Bekräftat leveransdatum

Leverantören kan också lägga till en anteckning eller bifogad fil.

På raderna kan leverantören ändra kvantiteten och leveransdatumet, lägga till anteckningar och bilagor, avvisa en rad, ersätta en rad med en annan produkt som ska anges som text och dela upp en rad i flera leveranser. Statusen för en rad varierar beroende på vilka ändringar som har föreslagits av leverantören:
    
- **Godkänd med ändringar**
- **Avvisad**
- **Ersatt** – I det här fallet läggs en extra rad till som har statusen **Ersättning**.
- **Bekräftat**
- **Dela upp i tidsplan** – I det här fallet läggs extra rader med statusen **Schemalägg rader** till.

Om en rad inte har några ändringar är radstatusen **Accepterad**.

I svaret kan du genom radstatus utläsa vilken typ av ändringar som gjorts av leverantören. Dessutom visas alla ändrade fält i fet stil, vilket hjälper dig att identifiera ändringarna.

Du kan uppdatera en inköpsorder genom att välja **Behandla uppdatering av inköpsorder** när du har fått svar eller på en rad i taget. Med hjälp av fältet **Är uppdateringen av inköpsorder behandlad?** i huvudet och på raderna kan du se om systemet har behandlat huvuden eller rader för att uppdatera inköpsordern med de ändringar som kommer från svaret. Du kan enbart köra åtgärden **Behandla uppdatering av inköpsorder** en gång per huvud eller rad.

Inte alla föreslagna ändringar kan uppdateras på en inköpsorder. Endast uppdateringar av rubriken och uppdateringar av datum och kvantiteter på raderna kan uppdateras automatiskt på inköpsordern. För andra ändringar måste du manuellt uppdatera inköpsordern. I detta fall kommer värdet på **Är uppdateringen av inköpsordern behandlad?** att vara **Manuell uppdatering**. Om till exempel en leverantör föreslår att en rad ska delas upp i en tidsplan måste ändringen göras manuellt.

Alla rader som har statusen **Godkänd** har ett bekräftat leveransdatum. När du kör åtgärden **Bearbeta uppdatering av inköpsorder** uppdateras datumet på inköpsordern. Anteckningar och bifogade filer överförs inte automatiskt till den aktuella inköpsordern. Handelsavtal utvärderas heller inte på inköpsorderraderna när du uppdaterar den aktuella inköpsordern via åtgärden **Behandla uppdatering av inköpsorder**.

## <a name="po-statuses-and-versions"></a>Statusar och versioner för inköpsorder

Det här avsnittet beskrivs olika statusvärden som en inköpsorder kan ha tills den har bekräftats. Här beskrivs också när nya versioner av inköpsordern görs tillgängliga för leverantören. Beteendet varierar beroende på om du använder ändringshantering för inköpsorder. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Versioner och status om du inte använder ändringshantering

Tabellen nedan visar ett exempel på förändringar i status och version som en IO kan gå igenom.

| Åtgärd | Status och version |
|--------|--------------------|
| Den första versionen av inköpsordern skapas i Finance and Operations. | Statusen är **Godkänd**. |
| Inköpsordern skickas till leverantören. | En version registreras i gränssnittet för leverantörssamarbete, och statusen ändras till **I extern granskning**. |
| Leverantören skickar svaret **Godkänd med ändringar**. | Statusvärdet är fortfarande **I extern granskning**. |
| Du gör några förändringar som begärs av leverantören. | Statusen ändras till **Approved**. |
| Du skickar den nya versionen av inköpsordern till leverantören. | En ny version registreras i gränssnittet för leverantörssamarbete, och statusen ändras till **I extern granskning**. |
| Leverantören godkänner den nya versionen av inköpsordern. | Statusvärdet är fortfarande **I extern granskning** såvida inte leverantörskontot har konfigurerats att automatiskt ange inköpsorder till statusen **Bekräftad** när leverantören godkänner dem. |

Leverantörer måste inte bekräfta en inköpsorder med hjälp av gränssnittet leverantörssamarbete. De kan också skicka ett e-postmeddelande eller kommunicera deras godkännande av en inköpsorder via andra kanaler. Du kan sedan bekräfta ordern manuellt i Finance and Operations. I det här fallet får du en varning om att ordern bekräftas, även om det inte finns något svar från leverantören. Inköpsordern visas sedan i bekräftelsehistoriken som en öppen, bekräftad order som inte har fått några svar. Leverantören har vid den här punkten inte längre möjlighet att bekräfta eller avvisa inköpsordern.

> [!NOTE]
> Den version av inköpsordern som är tillgänglig för andra processer i Finance and Operations är alltid den senaste versionen, även om denna version ännu inte har registrerats i gränssnittet leverantörssamarbete.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Versioner och status om du använder ändringshantering

Om du har inaktiverat ändringshantering för inköpsorder, kommer inköpsordern att genomgå ett arbetsflöde för godkännande för att nå statusen **Godkänd**. Denna process är inte synlig för leverantören.

Tabellen nedan visar ett exempel på förändringar i statusen och versionen som en IO kan gå igenom när ändringshantering är aktiverad. En version registreras när inköpsordern godkänns, inte när inköpsordern skickas till leverantören eller bekräftas.

| Åtgärd | Status och version |
|--------|--------------------|
| Den första versionen av inköpsordern skapas i Finance and Operations. | Statusen är **Utkast**. |
| IO:n är skickad till godkännandeprocessen. (Godkännandeprocessen är en intern process som leverantören inte är inblandad i.) | Statusvärdet ändras från **Utkast** till **Under granskning** till **Godkännande** om IO:n inte avvisas under godkännandeprocessen. Den godkända inköpsordern registreras som en version. | 
| Inköpsordern skickas till leverantören. | Versionen registreras i gränssnittet för leverantörssamarbete, och statusen ändras till **I extern granskning**. |
| Du kan göra några ändringar som begärts av leverantören, antingen manuellt eller genom att använda åtgärden **Bearbeta uppdatering av inköpsorder** på svaret för att uppdatera inköpsordern. | Statusen ändras tillbaka till **Utkast**. |
| IO:n skickas till godkännandeprocessen igen. | Statusvärdet ändras från **Utkast** till **Under granskning** till **Godkännande** om IO:n inte avvisas under godkännandeprocessen. Alternativt kan systemet konfigureras så att specifika fältändringar inte kräver nytt godkännande. I det här fallet ändras statusen först till **Utkast** och sedan uppdateras automatiskt till **Godkänd**. Den godkända inköpsordern registreras som en ny version. |
| Du skickar den nya versionen av inköpsordern till leverantören. | Den nya versionen registreras i gränssnittet för leverantörssamarbete, och statusen ändras till **I extern granskning**. |
| Leverantören godkänner den nya versionen av IO:n. | Statusen ändras till **Bekräftad** antingen automatiskt eller när du får svar från leverantören och sedan bekräftar IO:n. |

## <a name="sharing-information-about-consignment-inventory"></a>Dela information om försändelselager

Om du använder försändelselager, kan leverantörerna använda gränssnittet för leverantörssamarbete för att visa information på följande sidor:

- **Inköpsorder som förbrukar försändelselager** – Inköpsorder för försändelselager skapas när ägarskapet för lagret ändras från leverantören till ditt företag. En produktinleverans bokförs samtidigt. Dessa försändelseinköpsorder visas bara på sidan **Inköpsorder som förbrukar försändelselager**. De inkluderas inte på sidan **Alla bekräftade inköpsorder** i modulen **Leverantörssamarbete**.
- **Mottagna produkter från försändelselager** – Den här sidan visar alla transaktioner där ägarskapet för produkter har överförts från leverantören till ditt företag. Leverantörer kan använda den här informationen för att fakturera kunden.
- **Behållning i försändelselager** – Den här sidan visar det leverantörsägda, tillgängliga försändelselagret som har inlevererats på ditt lagerställe.

## <a name="working-with-rfqs-when-you-use-vendor-collaboration"></a>Arbeta med anbudsförfrågningar när du använder leverantörssamarbete

Det här avsnittet beskriver interaktioner mellan kunder och leverantörer vid anbudsförfråganprocessen. Här förklaras också hur information skickas till leverantörerna. En grundläggande översikt över stödet för anbudsförfråganprocessen finns i [Anbudsförfrågningar](request-quotations.md).

### <a name="alternates-attachments-amendments-and-returns"></a>Alternativ, bilagor, ändringar och returer

- **Alternativ** – I huvudet till en anbudsförfrågan kan du ange att alternativ tillåts för artikelrader inte finns i kataloger. När alternativ aktiveras kan leverantörer lägga till en alternativ rad för varje begärd rad.
- **Bilagor** – Bilagor kan läggas till på både huvudnivå och radnivå för en anbudsförfrågan. Bilagor kan klassificeras som antingen interna eller externa. Interna bilagor kan bara visas på kundens sida, medan leverantörer kan visa externa bilagor när de har skickats.

    Leverantörer kan också lägga till bilagor i sina budsvar. Dessa bilagor kan visas på kundens sida när en leverantör har skickat budsvaret. Bilagor som leverantörer lägger till klassificeras alltid som externa. Du får tillgång till en bilaga som en leverantör har lämnat in tillsammans med ett bud genom att välja **Budbilagor** eller **Radbilagor för bud**.
    
    Du öppnar bilagor som har skickats tillsammans med anbudsförfrågningar med hjälp symbolen med dokumentgemet i svaret.

- **Ändringar** – När en ändring har slutförts tas de befintliga budsvaren bort så att de kan ersättas med uppdaterade värden. Information som radpris och kvantitet från föregående budsvar kan visas via journalerna för anbudsförfrågan.

    Om du vill att ändringsprocessen ska vara tvingande går du till sidan **Anskaffnings- och källparametrar**, snabbfliken **Anbudsförfrågningar** och anger alternativet **Låser anbudsförfrågningar när de skickas** till **Ja**. (Det här alternativet är inställt och obligatoriskt för den offentliga sektorn.)

- **Returer** – Om en leverantör har skickat ett bud, men mer eller ändrad information krävs för anbudsförfrågan, kan kunden returnera budet till leverantören. Uppgifterna från budet som skickades tidigare bevaras, och leverantören kan göra de begärda ändringarna utan att behöva starta om budprocessen.

## <a name="public-sector-extensions"></a>Tillägg för offentlig sektor

Med de utökade funktionerna för den offentliga sektorn går det att skicka en anbudsförfrågan till leverantörer och publicera den. När du publicerar en anbudsförfrågan kan alla som begär informationen visa det arbete som omfattas av offentlighetsprincipen. Allt tillgängligt arbete återspeglas på listsidan **Öppna publicerad anbudsförfrågningar**, och annullerade, väntande eller beviljade anbudsförfrågningar kan visas på listsidan **Stängda publicerade anbudsförfrågningar**. Dessa dokument kan även visas på en plats utanför Finance and Operations genom integrationer med följande datatabeller:

- Publicerade anbudsförfrågningar
- Rad för publicerade anbudsförfrågningar
- Huvudbilagor för publicerade anbudsförfrågningar

Med dessa enheter kan personer som inte är allokerade användare i Finance and Operations, men som har åtkomst till den externa platsen, visa tillgängligt och avslutat arbete. Med de utökade funktionerna i **Skicka och publicera** kan användare som ställer in parametrar för anbudsförfråganprocessen dessutom definiera en e-postmall. När prokuristen sedan skapar anbudsförfrågan måste han eller hon välja e-postmallen för att kunna skicka den begärda informationen till leverantörerna i ärendet. 

Den användare som ställer in parametrarna för anbudsförfråganprocessen kan skapa flera e-postmallar. Dessa e-postmallar kan innehålla både statisk text och följande utbytestoken. Dessa token ersätts med sammanhangsberoende värden när ett e-postmeddelande skapas.

- %RFQCase%
- %RFQCaseName%
- %bidType%
- %inviteOnly%
- %expiryDateTime%
- %requester%
- %requestingDepartment%
- %accountnum%
- %todaysdate%
- %createddate%

Om en ändring krävs och skickas efter att en anbudsförfrågan har skickats, skickas anbudsförfrågan på nytt till alla inbjudna leverantörer. Det publicerade dokumentet uppdateras också på sidan **Öppna publicerad anbudsförfrågningar**.

