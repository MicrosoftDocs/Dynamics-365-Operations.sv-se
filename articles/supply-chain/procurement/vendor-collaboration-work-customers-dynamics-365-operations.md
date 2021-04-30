---
title: Leverantörssamarbete med kunder
description: I det här avsnittet beskrivs hur du kan använda leverantörssamarbete för att arbeta med inköpsorder och övervaka försändelselager.
author: TaylorVH
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart, VendVendorProfileCard, PurchVendorPortalAllResponse, PurchVendorPortalPendingResponsesPart, PurchVendorPortalResponses, PurchVendorPortalConfirmedOpenOrdersPart
audience: Application User
ms.reviewer: roschlom
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: v-savanh
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 5931d718d34db81ebd032eda821f071d9d329a26
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908045"
---
# <a name="vendor-collaboration-with-customers"></a>Leverantörssamarbete med kunder

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du kan använda leverantörssamarbete när du arbetar med kunder i Microsoft Dynamics 365 Supply Chain Management. Leverantörer kan utföra en rad olika affärsprocesser från följande arbetsytor:

- **Bekräftelse av inköpsorder** – Övervaka och svara på inköpsorder.
- **Budgivning av leverantör** – Visa anbudsförfrågningar och svara på dem genom att lämna anbud.
- **Leverantörsinformation** – Visa och uppdatera huvuddata för leverantör.
- **Fakturera** – Arbeta med fakturor. Det här avsnittet omfattar inte arbetsytan **Fakturering**. Mer information om den här arbetsytan finns i [Arbetsyta för leverantörssamarbetesfakturering](../../finance/accounts-payable/vendor-portal-invoicing-workspace.md).

Leverantörer kan också övervaka information om försändelsen.

## <a name="working-with-pos-in-the-purchase-order-confirmation-workspace"></a>Arbeta med inköpsorder i arbetsytan Inköpsorderbekräftelse

I arbetsytan **Inköpsorderbekräftelse** kan du besvara de inköpsorder som har skickats till dig för granskning. Här kan du också visa information om inköpsorder som inväntar åtgärd från kunden, samt inköpsorder som har bekräftats men som fortfarande är öppna.

Det finns tre listor i arbetsytan **Inköpsorderbekräftelse**:

- **Inköpsorder för granskning** – Denna lista visar inköpsorder som har skickats till dig och som inväntar ett svar från dig. När du har svarat tas inköpsordern bort från listan. Om kunden skickar dig en ny version av inköpsordern innan du har svarat på föregående version, visas bara den senaste versionen.
- **Inväntar kundåtgärd** – Den här listan visar alla de inköpsorder som du har svarat på, men som ännu inte har bekräftats. Om du godkänner en inköpsorder kan du övervaka den i den här listan, tills dess att statusen ändras till **Bekräftad**. Om du avvisar inköpsordern eller godkänner den med ändringar, kan du övervaka inköpsordern här tills kunden skickar en ny version.
- **Öppna bekräftade inköpsorder** – Denna lista visar alla inköpsorder för kontot som har statusen **Bekräftad**. När produkter eller tjänster har inlevererats helt mot inköpsordern, försvinner inköpsordern från listan.

Du kan använda följande sidor när du arbetar med inköpsorder:

- **Inköpsorder för granskning** – Den här sidan innehåller samma information som listan **Inköpsorder för granskning** i arbetsytan. Se beskrivningen tidigare i det här avsnittet.
- **Bekräftelsehistorik för inköpsorderleverantör** – Den här sidan innehåller alla inköpsorder och alla versioner av inköpsorder som har skickats till leverantören. Den innehåller även alla svar som har returnerats från leverantören.
- **Öppna bekräftade inköpsorder** Den här sidan innehåller samma information som listan **Öppna bekräftade inköpsorder** i arbetsytan. Se beskrivningen tidigare i det här avsnittet.
- **Alla bekräftade inköpsorder** – Den här sidan innehåller alla inköpsorder som har bekräftats. Inköpsorder på den här sidan omfattar de inköpsorder där produkter eller tjänster har inlevererats. Via denna lista kan du övervaka inköpsorder som du kan skicka fakturor för.

### <a name="responding-to-pos"></a>Besvara inköpsorder

De inköpsorder som kunden skickar dig för granskning visas i arbetsytan **Inköpsorderbekräftelse** och på sidan **Inköpsorder för granskning**. När du har öppnat en inköpsorder kan du godkänna den, avvisa den eller acceptera den med ändringar. Det kan finnas bilagor i inköpsorderhuvudet eller på enskilda rader. Du kan även bifoga information för ditt svar i inköpsorderhuvudet eller på enskilda rader. Du kan till exempel föreslå en reservartikel för en av raderna.

Du kan granska och skriva ut inköpsordern som en PDF-fil genom att använda alternativet **Förhandsgranska/Skriv ut**. Du kan också använda åtgärden **Visa dimensioner** om du vill dölja eller visa följande dimensionskolumner: **Plats**, **Lagerställe**, **Färg**, **Storlek**, **Stil** och **Konfiguration**. 

Om du använder alternativet **Acceptera ändringar** kan du godkänna eller avvisa enskilda rader. Du kan även göra följande ändringar på rader:

- Ändra datum eller kvantiteter. Om du vill uppdatera det bekräftade leveransdatumet på alla rader, använd alternativet **Uppdatera leveransdatum** i inköpsorderhuvudet.
- Dela rader för andra leveransdatum eller kvantiteter.
- Byt ut en artikel. Ange en artikelbeskrivning samt ditt artikelnummer i fältet **Extern** i avsnittet **Radinformation**.

Du kan inte ändra prissättningsinformation eller avgifter, men du kan föreslå ändringar genom att skriva anteckningar.

Om kunden skickar dig en ny version av en inköpsorder, kommer denna att bära ett versionstillägg som visar att den är en modifierad version av en inköpsorder som tidigare skickats. På sidan **Bekräftelsehistorik för inköpsorderleverantör** kan du spåra historiken för respektive order.

## <a name="monitoring-consignment-inventory"></a>Övervaka försändelselager

Om du använder försändelselager kan du använda gränssnittet för leverantörssamarbete för att visa information på följande sidor:

- **Inköpsorder som förbrukar försändelselager** – Inköpsorder för försändelselager skapas när kunden tar över ägarskapet för lagret. Dessa inköpsorder för försändelser visas endast på den här sidan. Alla ingår inte på sidan **Alla bekräftade inköpsorder**.
- **Mottagna produkter från försändelselager** – Den här sidan visar alla transaktioner där ägarskapet för produkter har överförts till det företag som har förbrukat lagret. Du kan använda den här informationen för att fakturera kunden.
- **Behållning i försändelselager** – Den här sidan visar det tillgängliga försändelselager som ägs av ditt företag men som är tillgängligt i kundens lager.

## <a name="working-with-rfqs-in-the-vendor-bidding-workspace"></a>Arbeta med anbudsförfrågningar i arbetsytan Budgivning av leverantör

I arbetsytan **Budgivning av leverantör** kan du visa anbudsförfrågningar som företaget har bjudits in att svara på. Du kan också svara på anbudsförfrågningarna. 

I arbetsytan visas också alla anbudsförfrågningar som du har vunnit eller förlorat. Om systemet är konfigurerat för den offentliga sektorn, visar arbetsytan dessutom anbudsförfrågningar som är offentligt tillgängliga.

### <a name="viewing-rfqs"></a>Visa anbudsförfrågningar

Öppna arbetsytan **Budgivning av leverantör** för att få tillgång till följande information:

- Välj **Nya budinbjudningar** för att visa vilka anbudsförfrågningar som ditt företag har svarat på. Härifrån kan du visa en anbudsförfrågan och börja budgivningen. Du ser också visa ändrade anbudsförfrågningar som du måste lämna ett nytt bud på.
- Välj **Returnerade bud** för att visa anbudsförfrågningar som kunden har returnerat till dig så att du kan lämna mer information eller uppdatera budet.
- Välj **Pågående bud** för att visa anbudsförfrågningar som du eller en kontaktperson som representerar ditt företag har arbetat men ännu inte skickat.
- Välj **Beviljade bud** för att visa när kunden har beviljat minst en radartikel i ditt bud.
- Välj **Förlorade bud** för att visa buden där alla rader har avvisats.
- Välj länken **Anbudsförfrågningar** för att visa en lista över leverantörens alla inbjudningar till anbudsförfrågningar och alla bud som har skickats. På sidan **Anbudsförfrågningar** finns en lista med alla anbudsförfrågningar som en leverantör har varit involverad i. Du kan söka utifrån status.
- Välj länken **Avvisade bud** för att visa en lista över alla anbudsförfrågningar där en leverantörs kontaktperson har avvisat att buda.

### <a name="working-with-rfqs-that-are-publicly-available"></a>Arbeta med anbudsförfrågningar som är offentligt tillgängliga

Personer som arbetar inom den offentliga sektorn kan visa öppna och utgångna anbudsförfrågningar som har gjorts tillgängliga för allmänheten.

- Välj länken **Öppna publicerade anbudsförfrågningar** för att visa en lista över öppna anbudsförfrågningar som är tillgängliga för allmänheten. En öppen anbudsförfrågan är en anbudsförfrågan som ännu inte har gått ut. Utgångsdatum och -tid finns i huvudet till anbudsförfrågan.

    Om du har blivit inbjuden att buda hittar du samma anbudsförfrågan på sidan **Nya budinbjudningar**. Ibland kanske du vill lämna bud på en öppen anbudsförfrågan, men du har inte blivit inbjuden att buda. I detta fall måste du kanske bjuda in dig själv, förutsatt att kunden har aktiverat självinbjudan för denna anbudsförfrågan.

    Förbättra tillgängligheten för länken **Öppna publicerade begäran om offert** genom att aktivera funktionen **Visa "Öppna publicerade begäran om offert" som en panel** feature. Med den här funktionen konverteras länken till en panel och flyttas till en väl synlig plats, så att det går lätt att hitta den.

- Välj länken **Stängda publicerade anbudsförfrågningar** för att visa en lista över stängda anbudsförfrågningar som är tillgängliga för allmänheten. En stängd anbudsförfrågan är en anbudsförfrågan har utgått. Utgångsdatum och -tid finns i huvudet till anbudsförfrågan.

    En stängd anbudsförfrågan visar alla leverantörsbud ned till radnivå. När bud beviljas eller avslås, återspeglas den här informationen i den stängda anbudsförfrågan. Eventuella bilagor som ingår i budet är också tillgängliga.

> [!NOTE]
> Den här funktionen är bara tillgänglig om konfigurationen Offentlig sektor har aktiverats.

### <a name="bidding"></a>Budgivning

- Klicka på **Bud** att lämna bud på en anbudsförfrågan.

    När redigering har aktiverats för budfälten i huvudet och raderna i en anbudsförfrågan kan du skriva budet direkt i rutnätet. Du måste också ta ställning till eventuellt ytterligare information som ska läggas till i raddetaljerna.

    När du börjar arbeta med ett bud visas det i avsnittet **Pågående bud**.

    Du kan när som helst spara ett bud innan det har gått ut. Du kan gå tillbaka senare, göra klart budet och sedan skicka det. När du har skickat ett bud kan du återkalla och uppdatera det fram tills utgångsdatumet.

- Välj **Återställ från anbudsförfrågan** för att återställa de data du angett för ett bud och återgå till den ursprungliga anbudsförfrågan. Du kan återställa huvudet eller raden.
- Välj **Lägg till alternativ** eller **Ta bort alternativ** i rutnätet om du vill arbeta med alternativ.

    En del anbudsförfrågningar tillåter alternativa bud. Du kan ange alternativa bud endast för rader av typen **Kategori**, eftersom vissa artiklar inte kan läggas till som alternativ. 

- Välj **Bilaga till anbudsförfrågan** eller **Radbilaga till anbudsförfrågan** för att öppna bilagor som kunden har lagt till i en anbudsförfrågan. Välj **Budbilagor** eller **Radbilagor för bud** för att skicka bilagor tillsammans med budet.

    Det kan finnas enkäter som du måste svara på innan du har rätt att lämna ett bud.

- Välj **Avslå** om du inte vill lämna ett bud. När du har valt **Avslå** kan du inte återkalla åtgärden och lämna ett bud.

Du måste lämna ett nytt bud om en anbudsförfrågan ändras. Du hittar information om ändringen på fliken **Ändringar** på sidan Anbudsförfrågan. Ändrade anbudsförfrågningar visas på sidan **Nya budinbjudningar**.

## <a name="accessing-vendor-master-data-in-the-vendor-information-workspace"></a>Komma åt leverantörens huvuddata i arbetsytan Leverantörsinformation

Som leverantör kan du komma åt en del av den information som kunden underhåller i leverantörens huvudpost. Därför kan du hålla informationen uppdaterad. Om du vill uppdatera informationen måste du ha rollen Leverantörsadmin (extern).

De tillgängliga uppgifterna är leverantörens namn, adress, kontaktinformation, kontaktpersoner och deras kontaktinformation, ID-nummer, skatteregistreringsnummer, anskaffningskategorier som leverantören har godkänts för att sälja till kunden samt och information om certifikat.

## <a name="additional-resources"></a>Ytterligare resurser

[Hantera användare av leverantörssamarbete](manage-vendor-collaboration-users.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]