---
title: Ställ in en extern katalog för PunchOut eProcurement
description: Det här avsnittet beskriver hur en extern katalog eller PunchOut-katalog används för att samla in offertinformation från en leverantör och lägga till den i en rekvisition.
author: kamaybac
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchVendorPortalRequests, CatExternalCatalogConfiguration, CatCXMLCartLogList
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a816f6cff90b8292f66d73b12d328c3f56108957
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920567"
---
# <a name="set-up-an-external-catalog-for-punchout-e-procurement"></a>Ställ in en extern katalog för PunchOut eProcurement

[!include [banner](../includes/banner.md)]

Genom att använda den externa katalogen kan du säkerställa att produkt- och prisinformationen som du därefter bearbetar i Supply Chain Management är korrekt och aktuell. Rekvisitionen kan sedan godkännas och konverteras till en inköpsorder och en order kan läggas hos leverantören.

När den externa katalogen har ställts in och anställd förbereder en rekvisition finns det ett alternativ för att omdirigera till en extern plats, den externa katalogen, och återgå till varukorgen som skapades på den externa platsen. Detta meddelande är baserat på cXML-protokollet och måste ställas in mellan systemen för den köpande och den säljande organisationen

Om du vill ställa in kommunikationen måste din leverantör tillhandahålla uppgifter som du kan använda i konfiguration av den externa katalogen såsom identiteten för köparens företaget, till exempel ”DUNS” och ”DUNS-nummer”, autentiseringsuppgifter och webbadressen för åtkomst till leverantörens katalog.

## <a name="setting-up-an-external-catalog"></a>Ställa in en extern katalog

Den externa katalogen bör aktivera en medarbetare som registrerar en inköpsrekvisition som ska omdirigeras till en extern webbplats för val av produkter. Produkter som medarbetaren väljer från den externa katalogen returneras med aktuell prisinformation och härifrån kan de läggas till på inköpsrekvisitionen. Syftet är inte att göra det möjligt för medarbetare att göra en beställning på den externa webbplatsen. När du ställer in den externa katalogen måste du kontrollera att syftet med den site det går att komma åt via den externa katalogen är att samla in offertinformation, inte att lägga riktiga order.

### <a name="to-set-up-an-external-vendor-catalog-complete-the-following-tasks"></a>Om du vill ställa in en extern leverantörskatalog måste du göra följande:

1. Ställa in en kategorihierarki för anskaffning. För mer information, se [Ställ in policyer för anskaffningskategorihierarkier](tasks/set-up-policies-procurement-category-hierarchies.md).
2. Registrera leverantören i Supply Chain Management. Innan du kan ställa in konfigurationerna för åtkomst till en extern leverantörskatalog måste du ställa in leverantören och leverantörskontakten i Microsoft Dynamics 365. Dessutom måste leverantörens externa katalog läggs till i den valda anskaffningkategorin. Mer information om hur du registrerar leverantörer finns i [Hantera användare av leverantörssamarbete](manage-vendor-collaboration-users.md). Information om hur du tilldelar leverantörer till en anskaffningskategori finns i [Godkänna leverantörer för specifika anskaffningskategorier](tasks/approve-vendors-specific-procurement-categories.md).
3. Kontrollera att måttenheterna och valutan som leverantören använder har ställts in. Information om hur du skapar en måttenhet finns i [Hantera måttenheter](../pim/tasks/manage-unit-measure.md).
4. Konfigurera den externa leverantörskatalogen med hjälp av kraven för webbplatsen för din externa leverantörskatalog. Mer information om den här uppgiften finns i [Konfigurera externa leverantörskatalogen](#configure-the-external-vendor-catalog).
5. Testa leverantörens externa katalogkonfigurationer för att bekräfta att inställningarna är korrekta och att du kan komma åt leverantörens externa katalog. Använd åtgärden **Validera inställningar** för att validera meddelandet om begäran om inställning som du har definierat. Det här meddelandet ska åstadkomma att leverantörens externa katalogwebbplats öppnas i ett webbläsarfönster. Vid validering kan du inte beställa artiklar och tjänster från leverantören. Om du vill beställa artiklar och tjänster måste du använda leverantörens katalog från en inköpsrekvisition.
6. Aktivera den externa katalogen med hjälp av knappen **Aktivera katalog** på sidan **Externa kataloger**. Den externa katalogen måste aktiveras innan anställda kan använda den. Du kan när som helst inaktivera den externa katalogen.


## <a name="configure-the-external-vendor-catalog"></a>Konfigurera den externa leverantörskatalogen

Det här avsnittet innehåller mer information om uppgift 4 i föregående avsnitt.

1. Ange ett namn och en beskrivning för leverantörens externa katalog. Det namn du anger visas på vagnen som representerar den externa katalogen som visas för medarbetare som skapar en inköpsrekvisition. Medarbetare kan klicka på vagnen för att öppna katalogen på webbplatsen för leverantörens externa katalog.
2. Lägga till en bild med hjälp av åtgärden **Extern katalogbild**. Bilden visas på vagnen som representerar den externa katalogen som visas för medarbetarna som skapar en inköpsrekvisition. Observera att bildens bredd och höjd måste vara lika. Annars visas bilden inte korrekt.
3. Välj om webbplatsen för leverantörens externa katalog ska visas i samma webbläsarfönster som det där medarbetaren skapade rekvisitionen eller om den ska öppnas i ett nytt fönster.
4. Markera leverantören för katalogen. I listan **Juridiska personer** finns det en rad för varje juridisk person där leverantören är inställd. Om du vill tillåta användare att begära produkter direkt från leverantörskatalog i vissa juridiska personer men inte i andra kan du använda knappen **Neka åtkomst** eller **Tillåt åtkomst** för varje juridisk person som du vill att katalogen ska vara eller inte vara tillgänglig för.
5. Ange antalet dagar som en offert mottagen från en extern katalog är giltig och kan användas för inköpet från den externa leverantören i fältet **Standardutgångsdatum (dagar)**. När en offert skapas och hämtas från webbplatsen för leverantörens externa katalog är offerten giltig det aktuella systemdatumet och fortsätter vara giltig i det antal dagar du anger i det här fältet.
6. Klicka på knappen **Lägg till** för att starta mappningen av anskaffningskategorierna till den externa katalogen. Välj sedan en kategori i listan Kategorinamn. Listan över kategorier är en överordnad uppsättning kategorier som leverantören har kopplats till för alla juridiska personer som har ställts in för leverantören.

    > [!NOTE]
    > Anskaffningspolicyer används för att tillåta eller begränsa åtkomst till kategorier för juridisk person för inköp och mottagande driftenhet. Punchout till en extern katalog kräver åtkomst tillåts för minst de anskaffningskategorier som är mappade till katalogen.

7. Ställ in cXML för begärandemeddelandet som ska skickas till leverantören. Automatiskt genererade meddelandeformat är den minsta mallen som krävs för att starta en session. Fyll i värden för taggarna.

När som helst kan du ladda om den systemgenererade meddelandemallen genom att klicka på **Återställ meddelandeformat**. Observera att om du återställer meddelandeformatet kommer det aktuella meddelandet att ersätts med det automatiskt genererade meddelandeformatet som har tomma taggar.

### <a name="cxml-setup-message"></a>Installationsmeddelande för cXML
Nedan hittar du en beskrivning av de etiketter som ingår i mallen:

| Fält | beskrivning | 
|---------|---------|
|< Header >< From >< Credential domain=”” >|Domänen för köparens företag.|
|< Header >< From >< Credential>< Identity >< /Identity > | Identiteten för köparens företag.|
|< Header >< To >< Credential domain=”” > | Domänen för leverantören företag.|
|< Header >< To >< Credential>< Identity >< /Identity> | Identiteten för leverantörens företag.|
|< Header >< Sender >< Credential domain=”” > | Domänen för köparens företag.|
|< Header >< Sender >< Credential >< Identity >< /Identity> | Identiteten för köparens företag.|
|< Header >< Sender >< Credential >< SharedSecret >< /SharedSecret >|Den delade hemligheten för köparens företag.|
|< Request deploymentMode=”” >|Distributionstest eller -produktion.|
|< Request >< PunchOutSetupRequest >< SupplierSetup >< URL >< /URL>|URL för leverantörens PunchOut-slutpunkt.|

### <a name="extrinsic-elements"></a>Extrinsic-element

Ett yttre element är ytterligare information, till exempel ett användarnamn som baseras på en användare som stämplar ut. Det yttre elementet anges när PunchOut inträffar och kan skickas i meddelandet om begärandeinställningar.
Din leverantör kan ha ett krav för att ta emot ett extrinsic-element i förfrågan om inställningar. I sådana fall bör du lägga till extrinsic-elementet i listan över extrinsic-element i avsnittet **Meddelandeformatet** på sidan **Extern katalog**.
Ange ett namn för extrinsic-elementet som leverantören kan känna igen och mappa det till ett värde. Alternativen för värden är: Användarnamn, Användarens e-postadress eller Slumpmässigt värde.
Mer information om cXML-protokollet finns på: [cXML.org webbsida](http://cxml.org/).

## <a name="post-back-message"></a>Retroaktivt meddelande
Det retroaktiva meddelandet är det meddelande som tas emot från leverantören när användaren checkar ut från den externa webbplatsen och återgår till Supply Chain Management. Retroaktiva meddelanden kan inte konfigureras. Meddelandena är baserade på cXML-protokolldefinitionen. Här finns all information som kan ingå i det retroaktiva meddelandet som tas emot på en rekvisitionsrad.

| Meddelande mottaget från leverantör | Kopierad till rekvisitionsraden|
|------------------------------|----------------------------------------------------------|
|< ItemIn quantity=”” > |Antal|
|< ItemIn>< ItemID >< SupplierPartID >< /SupplierPartID >|Externt artikel-ID|
|< ItemDetail>< UnitPrice >< Money currency=”” >| Valuta|
|< ItemDetail >< UnitPrice >< Money >< /Money >| Pris per enhet|
|< ItemDetail >< Description ShortName=”” >|Produktnamn|
|< ItemDetail >< Description >< /Description >|Ingår i artikelbeskrivningen: Produktnamn om ShortName inte har angetts.|
|< ItemDetail >< UnitOfMeasure >< /UnitOfMeasure >|Enhet|
|< ItemDetail >< Classification >< /Classification >|Ingår i artikebeskrivningen|
|< ItemDetail >< Classification domain=”” >|Ingår i artikebeskrivningen|

## <a name="delete-an-external-catalog"></a>Ta bort en extern katalog
Ta bort en extern katalog med åtgärden Ta bort på sidan.

Om en produkt från den externa leverantörskatalogen har efterfrågats kan den externa leverantörskatalogen inte raderas. I stället är statusen för den externa leverantörskatalogen inaktiv. Om du vill ta bort åtkomsten till webbplatsen för den externa leverantörens katalog, men inte ta bort, ändra den externa katalogen till inaktiv.

## <a name="additional-resources"></a>Ytterligare resurser

- [Förbättringar i inköps-cXML](purchasing-cxml-enhancements.md)
- [Använd externa kataloger för PunchOut eProcurement](use-external-catalogs-for-punchout.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]