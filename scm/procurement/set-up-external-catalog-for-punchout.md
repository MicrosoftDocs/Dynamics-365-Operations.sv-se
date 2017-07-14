---
title: "Ställ in en extern katalog för PunchOut eProcurement"
description: "Det här avsnittet beskriver hur en extern katalog eller PunchOut-katalog används för att samla in offertinformation från en leverantör och lägga till den i en rekvisition."
author: BibiSp
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 2d853cb963471f81d7a2a09a0f7913722de8a417
ms.contentlocale: sv-se
ms.lasthandoff: 06/20/2017


---

# Ställ in en extern katalog för PunchOut eProcurement
<a id="set-up-an-external-catalog-for-punchout-eprocurement" class="xliff"></a>

Genom att använda den externa katalogen kan du säkerställa att produkt- och prisinformationen som du därefter bearbetar i Dynamics 365 for Finance and Operations, Enterprise edition, juli 2017 är korrekt och aktuell. Rekvisitionen kan sedan godkännas och konverteras till en inköpsorder och en order kan läggas hos leverantören.

När den externa katalogen har ställts in och anställd förbereder en rekvisition finns det ett alternativ för att omdirigera till en extern plats, den externa katalogen, och återgå till varukorgen som skapades på den externa platsen. Detta meddelande är baserat på cXML-protokollet och måste ställas in mellan systemen för den köpande och den säljande organisationen

Om du vill ställa in kommunikationen måste din leverantör tillhandahålla uppgifter som du kan använda i konfiguration av den externa katalogen såsom identiteten för köparens företaget, till exempel ”DUNS” och ”DUNS-nummer”, autentiseringsuppgifter och webbadressen för åtkomst till leverantörens katalog.

## Ställa in en extern katalog
<a id="setting-up-an-external-catalog" class="xliff"></a>

Den externa katalogen bör aktivera en medarbetare som registrerar en inköpsrekvisition som ska omdirigeras till en extern webbplats för val av produkter. Produkter som medarbetaren väljer från den externa katalogen returneras till Dynamics 365 for Finance and Operations med aktuell prisinformation och härifrån kan de läggas till på inköpsrekvisitionen. Syftet är inte att göra det möjligt för medarbetare att göra en beställning på den externa webbplatsen. När du ställer in den externa katalogen måste du kontrollera att syftet med den site det går att komma åt via den externa katalogen är att samla in offertinformation, inte att lägga riktiga order.

### Om du vill ställa in en extern leverantörskatalog måste du göra följande:
<a id="to-set-up-an-external-vendor-catalog-complete-the-following-tasks" class="xliff"></a>

1. Ställa in en kategorihierarki för anskaffning. För mer information, se [Ställ in policyer för anskaffningskategorihierarkier](/https://ax.help.dynamics.com/en/wiki/set-up-policies-for-procurement-category-hierarchies/).
2. Registrera leverantören i Finance and Operations. Innan du kan ställa in konfigurationerna för åtkomst till en extern leverantörskatalog måste du ställa in leverantören och leverantörskontakten i Microsoft Dynamics 365. Dessutom måste leverantörens externa katalog läggs till i den valda anskaffningkategorin. Mer information om hur du registrerar leverantörer i Microsoft Dynamics 365 finns i [Hantera leverantörssamarbetesanvändare](/procurement/manage-vendor-collaboration-users.md). Information om hur du tilldelar en leverantörer till en anskaffningskategori finns i [Godkänna leverantörer för specifika anskaffningskategorier](/https://ax.help.dynamics.com/en/wiki/approve-vendors-for-specific-procurement-categories/).
3. Kontrollera att måttenheterna och valutan som leverantören använder har ställts in. Information om hur du skapar en måttenhet finns i [Skapa måttenheter](/https://ax.help.dynamics.com/en/wiki/manage-unit-of-measure/).
4. Konfigurera den externa leverantörskatalogen med hjälp av kraven för webbplatsen för din externa leverantörskatalog. Mer information om denna uppgift finns i nästa avsnitt.
5. Testa leverantörens externa katalogkonfigurationer för att bekräfta att inställningarna är korrekta och att du kan komma åt leverantörens externa katalog. Använd åtgärden **Validera inställningar** för att validera meddelandet om begäran om inställning som du har definierat. Det här meddelandet ska åstadkomma att leverantörens externa katalogwebbplats öppnas i ett webbläsarfönster. Vid validering kan du inte beställa artiklar och tjänster från leverantören. Om du vill beställa artiklar och tjänster måste du använda leverantörens katalog från en inköpsrekvisition.
6. Aktivera den externa katalogen med hjälp av knappen **Aktivera katalog** på sidan **Externa kataloger**. Den externa katalogen måste aktiveras innan anställda kan använda den. Du kan när som helst inaktivera den externa katalogen.


## (4) Konfigurera den externa leverantörskatalogen
<a id="4-configure-the-external-vendor-catalog" class="xliff"></a>

Det här avsnittet innehåller mer information om uppgift 4 i föregående avsnitt.

1. Ange ett namn och en beskrivning för leverantörens externa katalog. Det namn du anger visas på vagnen som representerar den externa katalogen som visas för medarbetare som skapar en inköpsrekvisition. Medarbetare kan klicka på vagnen för att öppna katalogen på webbplatsen för leverantörens externa katalog.
2. Lägga till en bild med hjälp av åtgärden **Extern katalogbild**. Bilden visas på vagnen som representerar den externa katalogen som visas för medarbetarna som skapar en inköpsrekvisition. Observera att bildens bredd och höjd måste vara lika. Annars visas bilden inte korrekt.
3. Välj om webbplatsen för leverantörens externa katalog ska visas i samma webbläsarfönster som det där medarbetaren skapade rekvisitionen eller om den ska öppnas i ett nytt fönster.
4. Markera leverantören för katalogen. I listan **Juridiska personer** finns det en rad för varje juridisk person där leverantören är inställd. Om du vill tillåta användare att begära produkter direkt från leverantörskatalog i vissa juridiska personer men inte i andra kan du använda knappen **Neka åtkomst** eller **Tillåt åtkomst** för varje juridisk person som du vill att katalogen ska vara eller inte vara tillgänglig för.
5. Ange antalet dagar som en offert mottagen från en extern katalog är giltig och kan användas för inköpet från den externa leverantören i fältet **Standardutgångsdatum (dagar)**. När en offert skapas och hämtas från webbplatsen för leverantörens externa katalog är offerten giltig det aktuella systemdatumet och fortsätter vara giltig i det antal dagar du anger i det här fältet.
6. Klicka på knappen **Lägg till** för att starta mappningen av anskaffningskategorierna till den externa katalogen. Välj sedan en kategori i listan Kategorinamn. Listan över kategorier är en överordnad uppsättning kategorier som leverantören har kopplats till för alla juridiska personer som har ställts in för leverantören.
[!NOTE]
Anskaffningspolicyer används för att tillåta eller begränsa åtkomst till kategorier för juridisk person för inköp och mottagande driftenhet. Punchout till en extern katalog kräver åtkomst tillåts för minst de anskaffningskategorier som är mappade till katalogen.
7. Ställ in cXML för begärandemeddelandet som ska skickas till leverantören. Automatiskt genererade meddelandeformat är den minsta mallen som krävs för att starta en session. Fyll i värden för taggarna.

När som helst kan du ladda om den systemgenererade meddelandemallen genom att klicka på **Återställ meddelandeformat**. Observera att om du återställer meddelandeformatet kommer det aktuella meddelandet att ersätts med det automatiskt genererade meddelandeformatet som har tomma taggar.

### Installationsmeddelande för cXML
<a id="cxml-setup-message" class="xliff"></a>
Nedan hittar du en beskrivning av de etiketter som ingår i mallen:

| Fält | beskrivning | 
|---------|---------|
|< Rubrik >< Från >< Autentiseringdomän = ”” >|Domänen för köparens företag.|
|< Huvud >< Från >< Autentiseringsuppgifter >< Identitet >< /Identitet > | Identiteten för köparens företag.|
|< Rubrik >< Till >< Autentiseringdomän = ”” > | Domänen för leverantören företag.|
|< Huvud >< Till >< Autentiseringsuppgifter >< Identitet >< /Identitet > | Identiteten för leverantörens företag.|
|< Rubrik >< Avsändare >< Autentiseringdomän = ”” > | Domänen för köparens företag.|
|< Huvud >< Avsändare >< Autentiseringsuppgifter >< Identitet >< /Identitet > | Identiteten för köparens företag.|
|< Rubrik >< Avsändare > < Autentiseringsuppgifter >< SharedSecret >< /SharedSecret >|Den delade hemligheten för köparens företag.|
|< Begära deploymentMode = ”” >|Distributionstest eller -produktion.|
|< Begäran >< PunchOutSetupRequest >< SupplierSetup >< URL >< /URL>|URL för leverantörens PunchOut-slutpunkt.|

### Extrinsic-element
<a id="extrinsic-elements" class="xliff"></a>

Ett extrinsic-element är ytterligare information, till exempel ett användarnamn som baseras på en användare som loggar ut. Extrinsic-elementet anges när punchout inträffar och kan skickas i begärandemeddelandets inställningar.
Din leverantör kan ha ett krav för att ta emot ett extrinsic-element i förfrågan om inställningar. I sådana fall bör du lägga till extrinsic-elementet i listan över extrinsic-element i avsnittet **Meddelandeformatet** på sidan **Extern katalog**. Ange ett namn för extrinsic-elementet som leverantören kan känna igen och mappa det till ett värde. Alternativen för värden är: Användarnamn, Användarens e-postadress eller Slumpmässigt värde.
Mer information om cXML-protokollet finns på: http://cxml.org/

## Retroaktivt meddelande
<a id="post-back-message" class="xliff"></a>
Det retroaktiva meddelandet är det meddelande som tas emot från leverantören när användaren checkar ut från den externa webbplatsen och återgår till Finance and Operations. Retroaktiva meddelanden kan inte konfigureras. Meddelandena är baserade på cXML-protokolldefinitionen. Här finns all information som kan ingå i det retroaktiva meddelandet som tas emot på en rekvisitionsrad:

| Meddelande mottaget från leverantör | Kopierad till rekvisitionsraden i Finance and Operations|
|------------------------------|----------------------------------------------------------|
|< ItemIn quantity=”” > |Kvantitet|
|< ItemIn>< ItemID >< SupplierPartID >< /SupplierPartID >|Externt artikel-ID|
|< ItemDetail >< Enhetspris >< Valuta = ”” >| Valuta|
|< ItemDetail >< UnitPrice >< Valuta >< /Valuta >| Pris per enhet|
|< ItemDetail >< Beskrivning ShortName=”” >|Produktnamn|
|< ItemDetail >< Beskrivning >< /Beskrivning >|Ingår i artikelbeskrivningen: Produktnamn om ShortName inte har angetts.|
|< ItemDetail >< UnitOfMeasure >< /UnitOfMeasure >|Enhet|
|< ItemDetail >< Klassificering >< /Klassificering >|Ingår i artikebeskrivningen|
|< ItemDetail >< Klassificeringsdomän = ”” >|Ingår i artikebeskrivningen|

## Ta bort en extern katalog
<a id="delete-an-external-catalog" class="xliff"></a>
Ta bort en extern katalog med åtgärden Ta bort på sidan.

Om en produkt från den externa leverantörskatalogen har efterfrågats kan den externa leverantörskatalogen inte raderas. I stället är statusen för den externa leverantörskatalogen inaktiv. Om du vill ta bort åtkomsten till webbplatsen för den externa leverantörens katalog, men inte ta bort, ändra den externa katalogen till inaktiv.

