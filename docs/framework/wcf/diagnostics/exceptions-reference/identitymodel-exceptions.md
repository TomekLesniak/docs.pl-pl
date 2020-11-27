---
title: Wyjątki modelu IdentityModel
ms.date: 03/30/2017
ms.assetid: 4ef34497-8ff5-4621-b773-7731cc721231
ms.openlocfilehash: 08d81f4eb35d0f4bda3997d6ab4dfd0ec10407e1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275040"
---
# <a name="identitymodel-exceptions"></a>Wyjątki modelu IdentityModel

W tym temacie wymieniono wszystkie wyjątki wygenerowane przez IdentityModel.  
  
## <a name="exception-list"></a>Lista wyjątków  
  
|Kod zasobu|Bieżący ciąg|  
|-------------------|--------------------|  
|ValueMustBeOf2Types|Wartość tego argumentu musi być jednym z tych dwóch typów.|  
|SAMLSubjectNameIdentifierRequiresNameValue|Nazwa określona dla elementu SamlNameIdentifier nie może mieć wartości null ani długości 0.|  
|TraceCodeIssuanceTokenProviderEndSecurityNegotiation|Metoda IssuanceTokenProvider zakończyła negocjowanie zabezpieczeń.|  
|TraceCodeSecurityNewServerSessionKeyIssued|Serwer wystawił nowy klucz sesji zabezpieczeń.|  
|SAMLAttributeMissingNameAttributeOnRead|Brak wartości "name" dla odczytywanego elementu SamlAttribute lub ma on długość 0.|  
|UnknownICryptoType|Implementacja ICrypto nie jest obsługiwana.|  
|TraceCodeSecurityTokenProviderClosed|Dostawca tokenów zabezpieczających został zamknięty.|  
|SAMLUnableToLoadAdvice|Nie można załadować \<saml:advice> elementu.|  
|SAMLAuthenticationStatementMissingAuthenticationMethodOnRead|Brak atrybutu "No" odczytywania dla elementu SamlAuthenticationStatement lub ma on długość 0.|  
|UnsupportedTransformAlgorithm|Nieobsługiwany algorytm transformacji lub kanonizacji.|  
|SAMLAudienceRestrictionShouldHaveOneAudience|SamlAudienceRestrictionCondition musi zawierać co najmniej jednego odbiorcę (URI).|  
|SAMLEvidenceShouldHaveOneAssertion|SamlEvidence musi odwoływać się do co najmniej jednego elementu SamlAssertion według identyfikatora lub odwołania.|  
|SAMLAudienceRestrictionInvalidAudienceValueOnRead|Odczytywany SamlAudienceRestrictionCondition nie ma wartości w elemencie "odbiorców".|  
|X509ChainBuildFail|Nie można skompilować określonego łańcucha certyfikatów X. 509. Używany certyfikat ma łańcuch zaufania, którego nie można zweryfikować. Zastąp certyfikat lub Zmień certificateValidationMode.|  
|XDCannotFindValueInDictionaryString|Nie znaleziono określonego identyfikatora wartości w ciągu słownika.|  
|TraceCodeImportSecurityChannelBindingEntry|Uruchamianie ImportChannelBinding zabezpieczeń.|  
|PrivateKeyExchangeNotSupported|Klucz prywatny nie obsługuje specyfikacji programu Exchange.|  
|TokenProviderUnableToGetToken|Dostawca określonego tokenu nie może dostarczyć tokenu zabezpieczającego.|  
|SAMLEntityCannotBeNullOrEmpty|Określona jednostka elementu SamlAssertion nie może mieć wartości null ani być pusta.|  
|SAMLAssertionRequireOneStatement|Element SamlAssertion wymaga co najmniej jednej instrukcji. Upewnij się, że dodano co najmniej jeden SamlStatement do tworzonego elementu SamlAssertion.|  
|AESInvalidInputBlockSize|Rozmiar wejściowy musi być wielokrotnością określonych bajtów.|  
|AESCryptAcquireContextFailed|Nie można uzyskać kontekstu dostawcy CSP.|  
|SAMLAssertionRequireOneStatementOnRead|Odczytywany element SamlAssertion nie zawiera żadnych SamlStatement. Element SamlAssertion musi zawierać co najmniej jedną SamlStatement.|  
|TraceCodeSecuritySessionClosedFaultReceived|Sesja zabezpieczeń klienta odebrała błąd zamknięcia sesji z serwera.|  
|TraceCodeIssuanceTokenProviderRedirectApplied|Metoda IssuanceTokenProvider zastosowała nagłówek przekierowania.|  
|TraceCodeSecuritySessionClosedFaultSendFailure|Wystąpił błąd podczas wysyłania do klienta błędu zamkniętego sesji zabezpieczeń.|  
|ValueMustBeZero|Wartość tego argumentu musi być równa 0.|  
|SAMLUnableToResolveSignatureKey|Nie można rozpoznać SecurityKeyIdentifier znalezionego w podpisie elementu SamlAssertion. Nie można zweryfikować podpisu elementu SamlAssertion dla określonego wystawcy.|  
|X509IsNotInTrustedStore|Określony certyfikat X. 509 nie znajduje się w magazynie zaufanych osób.|  
|SAMLElementNotRecognized|Określony element nie jest obsługiwany.|  
|SAMLAuthorizationDecisionStatementMissingResourceAttributeOnRead|Brak atrybutu "Resource" dla odczytywanej SamlAuthorizationDecisionStatement lub ma on długość 0.|  
|SamlTokenMissingSignature|Element SamlAssertion nie jest podpisany. Element SamlAssertion można podpisać przez ustawienie SigningCredentials.|  
|ExpectedElementMissing|Brak oczekiwanego elementu z określoną przestrzenią nazw.|  
|NoKeyIdentifierClauseFound|W SecurityKeyIdentifier nie znaleziono żadnej klauzuli określonego typu.|  
|MissingPrivateKey|Klucz prywatny nie występuje w certyfikacie X. 509.|  
|UnexpectedEOFFromReader|Nieoczekiwany znacznik EOF z czytnika XML.|  
|UnsupportedKeyDerivationAlgorithm|Określony algorytm wyznaczania wartości klucza nie jest obsługiwany.|  
|TokenDoesNotSupportKeyIdentifierClauseCreation|Określony token nie obsługuje tworzenia określonej klauzuli identyfikatora klucza.|  
|LastMessageNumberExceeded|Wykryto naruszenie protokołu numer sekwencyjny.|  
|SymmetricKeyLengthTooShort|Określona długość określonego klucza symetrycznego jest za krótka.|  
|SAMLAuthorityBindingMissingAuthorityKindOnRead|Odnaleziony elemencie SamlAuthorityBinding nie zawiera elementu "AuthorityKind", którego brakuje lub ma długość 0.  Jest to niedozwolone.|  
|XmlTokenBufferIsEmpty|XmlTokenBuffer jest pusty.|  
|InvalidXmlQualifiedName|Oczekiwano kwalifikowanej nazwy XML, ale znaleziono nieprawidłową nazwę.|  
|SAMLAuthorityKindMissingName|Elementu XmlQualifiedName reprezentujący element "AuthorityKind" w elemencie SamlAuthorityBinding nie może mieć wartości null ani długości 0.|  
|AESCryptEncryptFailed|Nie można zaszyfrować określonych danych.|  
|AuthorizationContextCreated|Zostanie utworzony kontekst autoryzacji z określonym identyfikatorem.|  
|SamlSerializerUnableToReadSecurityKeyIdentifier|Element SamlSerializer nie zawiera SecurityTokenSerializer z możliwością odczytu SecurityKeyIdentifier. Jeśli używasz niestandardowego SecurityKeyIdentifier, musisz podać niestandardowy SecurityTokenSerializer.|  
|TraceCodeIssuanceTokenProviderServiceTokenCacheFull|Metoda IssuanceTokenProvider zmniejszyła pamięć podręczną tokenów usługi.|  
|TraceCodeSecurityTokenProviderOpened|Otwarto dostawcę tokenów zabezpieczających.|  
|PublicKeyNotRSA|Klucz publiczny nie jest kluczem RSA.|  
|InvalidReaderState|Określony stan jest nieprawidłowy dla podanego czytnika danych wejściowych.|  
|UnableToResolveReferenceUriForSignature|Nie można rozpoznać określonego identyfikatora URI w podpisie, aby obliczyć podsumowanie.|  
|EmptyBase64Attribute|Znaleziono pustą wartość dla wymaganej nazwy atrybutu base64 i przestrzeni nazw.|  
|SAMLSubjectRequiresConfirmationMethodWhenConfirmationDataOrKeyInfoIsSpecified|SubjectConfirmation SAML wymaga metody potwierdzenia, gdy określono dane potwierdzenia lub KeyInfo.|  
|SAMLAudienceRestrictionShouldHaveOneAudienceOnRead|Odczytywany SamlAudienceRestrictionCondition musi zawierać co najmniej jedną wartość "odbiorców". Nie znaleziono żadnych.|  
|TokenProviderUnableToRenewToken|Dostawca określonego tokenu nie może odnowić tokenu zabezpieczającego.|  
|AESIVLengthNotSupported|Określona usługa BITS IV nie jest obsługiwana. Obsługiwany jest tylko 128 bitów IV.|  
|SAMLAuthorityBindingMissingAuthorityKind|Element elemencie SamlAuthorityBinding musi zawierać element "AuthorityKind", który nie ma wartości null.|  
|TraceCodeSecuritySessionDemuxFailure|Komunikat przychodzący nie jest częścią istniejącej sesji zabezpieczeń.|  
|TokenRenewalNotSupported|Dostawca określonego tokenu nie obsługuje odnowienia tokenu.|  
|AtLeastOneReferenceRequired|W podpisie wymagane jest co najmniej jedno odwołanie.|  
|SAMLSignatureAlreadyRead|Podpis został już odczytany w potwierdzeniu SAML.|  
|AlgorithmAndPrivateKeyMisMatch|Określony algorytm i klucz prywatny nie są zgodne.|  
|EmptyTransformChainNotSupported|Pusty łańcuch transformacji nie jest obsługiwany.|  
|SspiWrapperEncryptDecryptAssert1|SSPIWrapper:: EncryptDecryptHelper&#124; "offset" jest poza zakresem.|  
|SspiWrapperEncryptDecryptAssert2|SSPIWrapper:: EncryptDecryptHelper&#124; "size" jest poza zakresem. SecurityTokenManagerCannotCreateAuthenticatorForRequirement = Menedżer tokenów zabezpieczających nie może utworzyć wystawcy uwierzytelnienia tokenu dla określonego wymagania.|  
|UnableToCreateKeyedHashAlgorithm|Nie można utworzyć elementu KeyedHashAlgorithm z określonej wartości dla określonego algorytmu podpisu.|  
|SAMLUnableToLoadAssertion|\<saml:assertion>Nie można załadować elementu.|  
|X509FindValueMismatchMulti|Określony X509FindType wymaga, aby typ argumentu findValue miał jedną z dwóch wartości. Argument findValue jest innego typu.|  
|TraceCodeSecurityIdentityDeterminationSuccess|Określono tożsamość dla elementu EndpointAddress.|  
|UndefinedUseOfPrefixAtElement|Określony prefiks, który jest używany w elemencie nie ma zdefiniowanej przestrzeni nazw.|  
|TraceCodeSecuritySessionResponderOperationFailure|Operacja sesji zabezpieczeń nie powiodła się na serwerze.|  
|CannotFindCert|Nie można znaleźć certyfikatu X. 509 przy użyciu określonych kryteriów wyszukiwania: StoreName, StoreLocation, findtype, findValue.|  
|X509InvalidUsageTime|Określony czas użycia certyfikatu X. 509 jest nieprawidłowy. Czas użytkowania nie przypada między wymaganym czasem NotBefore a NotAfter czasem.|  
|TraceCodeSecurityIdentityDeterminationFailure|Nie można określić tożsamości dla elementu EndpointAddress.|  
|AsyncObjectAlreadyEnded|Metoda End została już wywołana dla tego asynchronicznego obiektu wynikowego.|  
|ExternalDictionaryDoesNotContainAllRequiredStrings|Słownik zewnętrzny nie zawiera definicji dla wszystkich wymaganych ciągów. Określony ciąg nie jest dostępny w słowniku zdalnym.|  
|TraceCodeSecuritySessionKeyRenewalFaultReceived|Sesja zabezpieczeń klienta otrzymała z serwera błąd odnowienia klucza.|  
|SAMLActionNameRequired|Ciąg reprezentujący element SamlAction nie może mieć wartości null ani długości 0.|  
|SignatureVerificationFailed|Weryfikacja podpisu nie powiodła się.|  
|TraceCodeSecurityContextTokenCacheFull|Pamięć podręczna elementu SecurityContextSecurityToken jest pełna.|  
|SAMLAssertionMissingMajorVersionAttributeOnRead|Brak MajorVersion dla odczytywanego elementu SamlAssertion lub ma on długość 0.|  
|SamlAttributeClaimRightShouldBePossessProperty|Ten konstruktor SamlAttribute wymaga, aby prawo oświadczenia miało wartość System. IdentityModel. Claims. Rights. PossessProperty.|  
|AuthorizationPolicyEvaluated|Oceniana jest zasada z określonym identyfikatorem.|  
|SAMLUnableToLoadCondtions<!-- the misspelling here is deliberate. -->|\<saml:conditions>Nie można załadować elementu.|  
|AESKeyLengthNotSupported|Określony klucz usługi BITS nie jest obsługiwany. Obsługiwany jest tylko klucz BITS 128, 192 i 256.|  
|UserNameCannotBeEmpty|Nazwa użytkownika nie może być pusta.|  
|AlgorithmAndPublicKeyMisMatch|Określony algorytm i klucz publiczny nie są zgodne.|  
|SAMLUnableToLoadCondtion<!-- the misspelling here is deliberate. -->|\<saml:conditions>Nie można załadować elementu.|  
|SamlAssertionMissingSigningCredentials|Nie ustawiono SigningCredentials w elemencie SamlAssertion. Element SamlAssertion musi być podpisany. Aby można było wykonać operację, Ustaw prawidłowy SigningCredentials w elemencie SamlAssertion.|  
|SspiPayloadNotEncrypted|Dane binarne nie zostały zaszyfrowane za pomocą kontekstu zabezpieczeń SSPI.|  
|SAMLAuthorizationDecisionShouldHaveOneActionOnRead|Odczytywany SamlAuthorizationDecisionStatement nie zawiera żadnych element SamlAction.|  
|TraceCodeSecurityBindingSecureOutgoingMessageFailure|Protokół zabezpieczeń nie może zabezpieczyć wiadomości wychodzącej.|  
|UndefinedUseOfPrefixAtAttribute|Określony prefiks używany w konkretnym atrybucie nie ma zdefiniowanej przestrzeni nazw.|  
|NoInputIsSetForCanonicalization|Nie ustawiono danych wejściowych na potrzeby zapisywania kanonicznych danych wyjściowych.|  
|TraceCodeSecurityPendingServerSessionAdded|Do serwera zostanie dodana oczekująca sesja zabezpieczeń.|  
|Metoda AsyncCallbackexception|Metoda AsyncCallback zgłosiła wyjątek.|  
|PrivateKeyNotRSA|Klucz prywatny nie jest kluczem RSA.|  
|TraceCodeSecurityClientSessionKeyRenewed|Sesja zabezpieczeń klienta odnawia klucz sesji.|  
|SAMLAuthorizationDecisionStatementMissingDecisionAttributeOnRead|Brak elementu "decyzja" dla odczytywanej SamlAuthorizationDecisionStatement lub ma on długość 0.|  
|SAMLAttributeNameAttributeRequired|Element "name" określony dla elementu SamlAttribute nie może mieć wartości null ani długości 0.|  
|SamlSerializerRequiresExternalSerializers|Element SamlSerializer wymaga SecurityTokenSerializer do serializacji SecurityKeyIdentifier obecnego w tokenie.|  
|UnableToResolveKeyReference|Program rozpoznawania tokenów nie może rozpoznać określonego odwołania do klucza zabezpieczeń.|  
|UnsupportedKeyWrapAlgorithm|Algorytm zawijania określonego klucza nie jest obsługiwany.|  
|SAMLAssertionMissingIssuerAttributeOnRead|Brak elementu "Issuer" dla odczytywanego elementu SamlAssertion lub ma on długość 0.|  
|TraceCodeIssuanceTokenProviderUsingCachedToken|Metoda IssuanceTokenProvider użyła tokenu usługi w pamięci podręcznej.|  
|AESCryptGetKeyParamFailed|Nie można pobrać określonego parametru klucza.|  
|InvalidNamespaceForEmptyPrefix|Przestrzeń nazw jest nieprawidłowa dla pustego prefiksu.|  
|AESCipherModeNotSupported|Określony tryb szyfru nie jest obsługiwany. Obsługiwane są tylko CBC.|  
|ArgumentCannotBeEmptyString|Argument musi być niepustym ciągiem.|  
|SAMLAssertionMissingMinorVersionAttributeOnRead|Brak MinorVersion dla odczytywanego elementu SamlAssertion lub ma on długość 0.|  
|SpecifiedStringNotAvailableInDictionary|Określony ciąg nie jest pozycją w bieżącym słowniku.|  
|KerberosApReqInvalidOrOutOfMemory|Wartość AP-REQ jest nieprawidłowa lub system nie ma wystarczającej ilości pamięci.|  
|FailLogonUser|Funkcji LogonUser dla określonego użytkownika nie powiodło się. Upewnij się, że użytkownik ma prawidłowe konto systemu Windows.|  
|ValueMustBeNonNegative|Wartość tego argumentu nie może być ujemna.|  
|X509ValidationFail|Nie można zweryfikować określonego certyfikatu X. 509.|  
|TraceCodeSecuritySessionRequestorOperationSuccess|Operacja sesji zabezpieczeń została ukończona pomyślnie na kliencie.|  
|SAMLActionNameRequiredOnRead|Brak ciągu, który jest odczytywany dla element SamlAction lub ma długość 0.|  
|KerberosMultilegsNotSupported|Tożsamość jest określana jako nazwa UPN. Uwierzytelnianie usługi uruchomionej na koncie użytkownika wymaga wieloetapowego protokołu Kerberos, który jest nieobsługiwany.|  
|SAMLAssertionIdRequired|Element "assertionId" dla elementu SamlAssertion nie może mieć wartości null ani być pusty.|  
|InvalidOperationForWriterState|Określona operacja jest nieprawidłowa w określonym stanie XmlWriter.|  
|CannotValidateSecurityTokenType|Określony wystawca uwierzytelnienia tokenu zabezpieczającego nie może zweryfikować tokenu określonego typu.|  
|X509FindValueMismatch|Określony X509FindType wymaga typu argumentu findValue, który ma być określoną wartością. Argument findValue jest innego typu.|  
|TraceCodeSecurityClientSessionCloseSent|Sesja zabezpieczeń klienta wysłała komunikat zamknięcia.|  
|SuiteDoesNotAcceptAlgorithm|Określony algorytm nie został zaakceptowany dla określonej operacji przez określony pakiet algorytmu|  
|TraceCodeSecuritySessionRequestorOperationFailure|Operacja sesji zabezpieczeń klienta nie powiodła się.|  
|SAMLUnableToLoadStatement|Nie można załadować elementu SamlStatement.|  
|InnerReaderMustBeAtElement|Wewnętrzny czytnik musi znajdować się w elemencie.|  
|UnableToCreateTokenReference|Nie można utworzyć odwołania do tokenu zabezpieczającego.|  
|TraceCodeSecurityBindingIncomingMessageVerified|Protokół zabezpieczeń zweryfikował komunikat przychodzący.|  
|ObjectIsReadOnly|Obiekt jest tylko do odczytu.|  
|TraceCodeSecurityClientSessionPreviousKeyDiscarded|Sesja zabezpieczeń klienta odrzuciła poprzedni klucz sesji.|  
|SAMLTokenTimeInvalid|SamlToken nie jest prawidłowym czasem. Bieżący czas jest poza obowiązującym i nieupływem czasu wygaśnięcia tokenu.|  
|TraceCodeSecurityIdentityVerificationSuccess|Weryfikacja tożsamości zakończyła się pomyślnie.|  
|SigningTokenHasNoKeys|Określony token podpisujący nie ma kluczy.|  
|TraceCodeSecurityIdentityVerificationFailure|Weryfikacja tożsamości nie powiodła się.|  
|AESCryptImportKeyFailed|Importowanie materiału klucza nie powiodło się.|  
|FailInitializeSecurityContext|InitializeSecurityContent nie powiodła się. Upewnij się, że nazwa główna usługi jest poprawna.|  
|TraceCodeStreamSecurityUpgradeAccepted|Pomyślnie zaakceptowano uaktualnienie zabezpieczeń strumienia.|  
|SAMLAuthorityBindingRequiresLocation|Atrybut "Location" określony w elemencie SamlAuthorityBinding nie może mieć wartości null ani długości 0.|  
|PublicKeyNotDSA|Klucz publiczny nie jest kluczem DSA.|  
|ImpersonationLevelNotSupported|Tryby uwierzytelniania przy użyciu protokołu Kerberos nie obsługują określonego poziomu personifikacji. Określ prawidłowy identyfikator lub poziom personifikacji.|  
|RequiredTargetNotSigned|Element z określonym identyfikatorem musi być podpisany, ale nie był.|  
|SAMLAuthenticationStatementMissingAuthenticationInstanceOnRead|Brak atrybutu "AuthenticationInstant" dla elementu SamlAuthenticationStatement lub ma on długość 0.|  
|SAMLEvidenceShouldHaveOneAssertionOnRead|Odczytywany SamlEvidence nie zawiera odwołania do lub osadzonego elementu SamlAssertion.|  
|LengthOfArrayToConvertMustGreaterThanZero|Długość tablicy do przekonwertowania na liczbę całkowitą musi być większa niż 0.|  
|InvalidAsyncResult|Nieprawidłowy obiekt AsyncResult.|  
|TraceCodeIssuanceTokenProviderRemovedCachedToken|Metoda IssuanceTokenProvider usunęła wygasły token usługi.|  
|IncorrectUserNameFormat|Nazwa użytkownika ma nieprawidłowy format. Format nazwy użytkownika musi mieć postać "username" lub "Domain \\ \username.".|  
|TraceCodeExportSecurityChannelBindingEntry|Uruchamianie ExportChannelBinding zabezpieczeń.|  
|UnsupportedInputTypeForTransform|Określony typ danych wejściowych nie jest obsługiwany w przypadku transformacji.|  
|CannotFindDocumentRoot|Nie można znaleźć elementu głównego dokumentu.|  
|XmlBufferQuotaExceeded|Rozmiar wymagany do buforowania zawartości XML przekroczył limit przydziału buforu.|  
|TraceCodeSecuritySessionClosedResponseSendFailure|Wystąpił błąd podczas wysyłania do klienta odpowiedzi na zakończenie sesji zabezpieczeń.|  
|UnableToResolveReferenceInSamlSignature|Nie można rozpoznać określonego odwołania w podpisie SAML przy użyciu AssertionID.|  
|SAMLSubjectRequiresNameIdentifierOrConfirmationMethod|Element SamlSubject wymaga określenia elementu "NameIdentifier" lub "ConfirmationMethod". Brak obu tych wartości.|  
|SAMLAttributeMissingNamespaceAttributeOnRead|Brak wartości "namespace" dla odczytywanego elementu SamlAttribute lub ma on długość 0.|  
|SAMLSubjectConfirmationClauseMissingConfirmationMethodOnRead|Nie można odnaleźć elementu "ConfirmationMethod" w odczytywanym SamlSubjectConfirmation.|  
|SecurityTokenRequirementHasInvalidTypeForProperty|Wymaganie tokenu ma nieoczekiwany typ dla określonej właściwości. Oczekiwany typ właściwości ma inną wartość.|  
|TraceCodeNegotiationTokenProviderAttached|Dołączono NegotiationTokenProvider.|  
|TraceCodeSpnegoClientNegotiationCompleted|SpnegoTokenProvider ukończono negocjowanie interfejsu SSPI.|  
|SAMLUnableToLoadUnknownElement|Wybrany element SamlSerializer nie może zdeserializować tego elementu. Zarejestruj niestandardowy element SamlSerializer, aby deserializować elementy niestandardowe.|  
|CreateSequenceRefused|Żądanie utworzenia sekwencji zostało odrzucone przez miejsce docelowe Menedżera zasobów.|  
|TraceCodeSecuritySessionRedirectApplied|Sesja zabezpieczeń klienta została przekierowana.|  
|SecurityTokenRequirementDoesNotContainProperty|Wymaganie tokenu nie zawiera określonej właściwości.|  
|SAMLAttributeValueCannotBeNull|Znaleziono jedną z attributeValues w elemencie SamlAttribute jako wartość null. Upewnij się, że listy nie mają wartości null podczas tworzenia elementu SamlAttribute.|  
|ValueMustBeGreaterThanZero|Wartość tego argumentu musi być większa niż 0.|  
|TraceCodeNegotiationAuthenticatorAttached|Dołączono NegotiationTokenAuthenticator.|  
|ValueMustBePositive||  
|SAMLAuthorizationDecisionShouldHaveOneAction|Element SamlAuthorizationDecisionStatement musi mieć co najmniej jedną element SamlAction.|  
|TraceCodeSecurityTokenAuthenticatorClosed|Wystawca uwierzytelnienia tokenu zabezpieczającego został zamknięty.|  
|TraceCodeSecurityAuditWrittenSuccess|Dziennik inspekcji zabezpieczeń został pomyślnie zapisany.|  
|PrivateKeyNotDSA|Klucz prywatny nie jest kluczem DSA.|  
|MessageNumberRollover|Przekroczono maksymalny numer sekwencji dla tej sekwencji.|  
|AESPaddingModeNotSupported|Określony tryb uzupełniania nie jest obsługiwany. Obsługiwane są tylko PKCS7 i ISO10126.|  
|SAMLSubjectRequiresNameIdentifierOrConfirmationMethodOnRead|Nie znaleziono wymaganych elementów "NameIdentifier" i "ConfirmationMethod" dla odczytywanych SamlSubject.|  
|TraceCodeSecurityAuditWrittenFailure|Wystąpił błąd podczas zapisywania w dzienniku inspekcji zabezpieczeń.|  
|UnsupportedCryptoAlgorithm|Określony algorytm kryptograficzny nie jest obsługiwany w tym kontekście.|  
|SigningTokenHasNoKeysSupportingTheAlgorithmSuite|Token podpisujący nie ma klucza obsługującego określony pakiet algorytmów.|  
|SAMLNameIdentifierMissingIdentifierValueOnRead|Brak ciągu "identifier" dla odczytywanego SamlNameIdentifier.|  
|SAMLSubjectStatementRequiresSubject|Instrukcja SAML subject wymaga określenia elementu SAML Subject.|  
|TraceCodeSslClientCertMissing|Zdalny klient SSL nie mógł dostarczyć wymaganego certyfikatu.|  
|SAMLTokenVersionNotSupported|Określona wersja główna i wersja pomocnicza nie są obsługiwane.|  
|TraceCodeConfigurationIsReadOnly|Konfiguracja jest tylko do odczytu.|  
|TraceCodeSecuritySessionRenewFaultSendFailure|Wystąpił błąd podczas wysyłania błędu odnowienia z klucza sesji zabezpieczeń do klienta.|  
|TraceCodeSecurityInactiveSessionFaulted|Serwer napotkał błąd nieaktywnej sesji zabezpieczeń.|  
|SAMLUnableToLoadAttribute|Nie można załadować elementu SamlAttribute.|  
|Psha1KeyLengthInvalid|Określona długość klucza PSHA1: jest nieprawidłowa.|  
|KeyIdentifierCannotCreateKey|Ta SecurityKeyIdentifier nie ma żadnej klauzuli, która może utworzyć klucz.|  
|X509IsInUntrustedStore|Określony certyfikat X. 509 znajduje się w niezaufanym magazynie certyfikatów.|  
|UnexpectedXmlChildNode|Określony węzeł podrzędny XML określonego typu jest nieoczekiwany dla określonego elementu.|  
|TokenDoesNotMeetKeySizeRequirements|Wymagania dotyczące rozmiaru klucza dla określonego pakietu algorytmu nie są spełnione przez określony token.|  
|TraceCodeSecuritySessionRequestorStartOperation|Operacja sesji zabezpieczeń została uruchomiona na kliencie.|  
|InvalidHexString|Nieprawidłowy format ciągu szesnastkowego.|  
|SamlAttributeClaimResourceShouldBeAString|Ten konstruktor SamlAttribute wymaga, aby zasób żądania był typu "String".|  
|SamlSigningTokenNotFound|Element SamlAssertion jest podpisany, ale nie można odnaleźć tokenu, który podpisał element SamlAssertion. Upewnij się, że SecurityTokenResolver zawiera token, który podpisał element SamlAssertion.|  
|TraceCodeSecuritySpnToSidMappingFailure|Nie można zamapować elementu ServicePrincipalName do SecurityIdentifier.|  
|UnableToCreateSignatureFormatterFromAsymmetricCrypto|Nie można utworzyć programu formatującego sygnatury dla określonego algorytmu z określonego kryptografii asymetrycznej.|  
|TraceCodeSecurityServerSessionClosedFaultSent|Sesja zabezpieczeń serwera wysłała do klienta błąd zamknięty sesji.|  
|UnableToFindPrefix|Nie można znaleźć prefiksu dla określonego, widocznego prefiksu w określonym elemencie.|  
|TraceCodeSecurityTokenAuthenticatorOpened|Otwarto wystawcę uwierzytelnienia tokenu zabezpieczeń.|  
|RequiredAttributeMissing|Określony atrybut jest wymagany w określonym elemencie.|  
|LocalIdCannotBeEmpty|LocalId nie może być pusty. Określ prawidłową wartość "localId".|  
|ValueMustBeInRange|Wartość tego argumentu musi należeć do określonego zakresu.|  
|TraceCodeIssuanceTokenProviderBeginSecurityNegotiation|Metoda IssuanceTokenProvider uruchomiła nowe negocjowanie zabezpieczeń.|  
|InvalidNtMapping|Nie można zamapować określonego certyfikatu X. 509 na konto systemu Windows. Alternatywna nazwa podmiotu nazwy UPN jest wymagana.|  
|AESCryptSetKeyParamFailed|Ustawienie określonego parametru klucza nie powiodło się.|  
|TraceCodeSecuritySessionClosedResponseReceived|Sesja zabezpieczeń klienta otrzymała z serwera zamknął odpowiedź.|  
|UnableToCreateSignatureDeformatterFromAsymmetricCrypto|Nie można utworzyć elementu unformatującego sygnatury dla określonego algorytmu z określonego kryptografii asymetrycznej.|  
|TraceCodeIdentityModelAsyncCallbackThrewException|Asynchroniczne wywołanie zwrotne wywołało wyjątek.|  
|LengthMustBeGreaterThanZero|Długość tego argumentu musi być większa niż 0.|  
|FoundMultipleCerts|Znaleziono wiele certyfikatów X. 509 przy użyciu określonych kryteriów wyszukiwania: StoreName, StoreLocation, findtype, findValue. Podaj bardziej konkretną wartość wyszukiwania.|  
|AtLeastOneTransformRequired|Element transformacje musi zawierać co najmniej jedno przekształcenie.|  
|SAMLTokenNotSerialized|Nie można serializować elementu SamlAssertion do kodu XML. Aby uzyskać szczegółowe informacje, zobacz wyjątek wewnętrzny.|  
|TraceCodeSecurityBindingOutgoingMessageSecured|Protokół zabezpieczeń przyzabezpieczony komunikat wychodzący.|  
|KeyIdentifierClauseDoesNotSupportKeyCreation|Ten SecurityKeyIdentifierClause nie obsługuje tworzenia kluczy.|  
|UnableToResolveTokenReference|Program rozpoznawania tokenów nie może rozpoznać określonego odwołania do tokenu.|  
|UnsupportedEncryptionAlgorithm|Określony algorytm szyfrowania nie jest obsługiwany.|  
|SamlSerializerUnableToWriteSecurityKeyIdentifier|Element SamlSerializer nie zawiera SecurityTokenSerializer z możliwością serializacji danego SecurityKeyIdentifier. Jeśli używasz niestandardowego SecurityKeyIdentifier, musisz podać niestandardowy SecurityTokenSerializer.|  
|SAMLAttributeShouldHaveOneValue|Nie znaleziono wartości atrybutów. Atrybut SamlAttribute musi mieć co najmniej jedną wartość atrybutu.|  
|TraceCodeSecurityBindingVerifyIncomingMessageFailure|Protokół zabezpieczeń nie może zweryfikować komunikatu przychodzącego.|  
|SamlSigningTokenMissing|Element SamlAssertion przesłany do SamlSecurityTokenAuthenticator nie zawiera tokenu podpisywania.|  
|NoPrivateKeyAvailable|Brak dostępnego klucza prywatnego.|  
|ValueMustBeOne|Wartość tego argumentu musi być równa 1.|  
|TraceCodeSecurityPendingServerSessionRemoved|Oczekująca sesja zabezpieczeń została uaktywniona przez serwer.|  
|TraceCodeImportSecurityChannelBindingExit|Zakończono ImportChannelBinding zabezpieczeń.|  
|X509CertStoreLocationNotValid|StoreLocation musi mieć wartość LocalMachine lub CurrentUser.|  
|SettingdMayBeModifiedOnlyWhenTheWriterIsInStartState|Ustawienia składnika zapisywania mogą być modyfikowane tylko wtedy, gdy moduł zapisujący jest w stanie początkowym.|  
|ArgumentInvalidCertificate|Certyfikat jest nieprawidłowy.|  
|DigestVerificationFailedForReference|Weryfikacja skrótu nie powiodła się dla określonego odwołania.|  
|SAMLAuthorityBindingRequiresBinding|Atrybut "Binding" określony w elemencie SamlAuthorityBinding nie może mieć wartości null ani długości 0.|  
|AESInsufficientOutputBuffer|Bufor wyjściowy musi być większy niż określona liczba bajtów.|  
|SAMLAuthorityBindingMissingBindingOnRead|Brak atrybutu "Binding" dla odczytywanej elemencie SamlAuthorityBinding lub ma on długość 0.|  
|SAMLAuthorityBindingInvalidAuthorityKind|Odczytywany elemencie SamlAuthorityBinding ma nieprawidłowy AuthorityKind. Format AuthorityKind musi być QName.|  
|ProvidedNetworkCredentialsForKerberosHasInvalidUserName|Element NetworkCredentials podany dla tokenu Kerberos nie ma prawidłowej nazwy użytkownika.|  
|SSPIPackageNotSupported|Określony pakiet SSPI nie jest obsługiwany.|  
|TokenCancellationNotSupported|Dostawca określonego tokenu nie obsługuje anulowania tokenu.|  
|UnboundPrefixInQName|W określonej kwalifikowanej nazwie użyto niezwiązanego prefiksu.|  
|SAMLAuthorizationDecisionResourceRequired|Określony element "Resource" SamlAuthorizationDecisionStatement nie może mieć wartości null ani długości 0.|  
|TraceCodeSecurityNegotiationProcessingFailure|Błąd przetwarzania negocjacji zabezpieczeń usługi.|  
|SAMLAssertionIssuerRequired|Element "Issuer" określony dla elementu SamlAssertion nie może mieć wartości null ani być pusty.|  
|UnableToCreateHashAlgorithmFromAsymmetricCrypto|Nie można utworzyć elementu algorytm dla określonego algorytmu z określonego kryptografii asymetrycznej.|  
|SamlUnableToExtractSubjectKey|Nie można rozpoznać elementu SecurityKeyIdentifier znajdującego się w SamlSubject w elemencie SecurityToken. SecurityTokenResolver musi zawierać element SecurityToken, do którego SecurityKeyIdentifier jest rozpoznawany.|  
|ChildNodeTypeMissing|Określony element XML nie ma elementu podrzędnego określonego typu.|  
|TraceCodeSecurityPendingServerSessionClosed|Oczekująca sesja zabezpieczeń została zamknięta przez serwer.|  
|TraceCodeSecuritySessionCloseResponseSent|Sesja zabezpieczeń serwera wysłała do klienta odpowiedź o zamknięciu.|  
|TraceCodeSecurityIdentityHostNameNormalizationFailure|Nie można znormalizować części nazwy hosta adresu punktu końcowego.|  
|FailAcceptSecurityContext|Działanie funkcji AcceptSecurityContext nie powiodła się.|  
|EmptyXmlElementError|Określony element nie może być pusty.|  
|PrefixNotDefinedForNamespace|Prefiks określonego obszaru nazw nie jest zdefiniowany w tym kontekście i nie można go zadeklarować.|  
|SAMLAuthorizationDecisionHasMoreThanOneEvidence|Znaleziono, że odczytywany SamlAuthorizationDecisionStatement zawiera więcej niż jeden dowód. Jest to niedozwolone.|  
|SamlTokenAuthenticatorCanOnlyProcessSamlTokens|SamlSecurityTokenAuthenticator może przetwarzać tylko SamlSecurityTokens. Odebrano określony element SecurityTokentype.|  
|SAMLAttributeStatementMissingAttributeOnRead|Odczytywany SamlAttributeStatement nie zawiera żadnych elementów "SamlAttribute". Jest to niedozwolone.|  
|CouldNotFindNamespaceForPrefix|Nie można wyszukać przestrzeni nazw dla określonego prefiksu.|  
|TraceCodeExportSecurityChannelBindingExit|Zakończono ExportChannelBinding zabezpieczeń.|  
|AESCryptDecryptFailed|Nie można odszyfrować określonych danych.|  
|SAMLAttributeNamespaceAttributeRequired|Element "namespace" określony dla elementu SamlAttribute nie może mieć wartości null ani długości 0.|  
|TraceCodeSpnegoServiceNegotiationCompleted|SpnegoTokenAuthenticator ukończono negocjowanie interfejsu SSPI.|  
|TraceCodeSecurityServerSessionRenewalFaultSent|Sesja zabezpieczeń serwera wysłała do klienta błąd odnowienia klucza.|  
|AlgorithmMismatchForTransform|Wystąpił niezgodność w algorytmie transformacji.|  
|UserNameAuthenticationFailed|Uwierzytelnianie nazwy użytkownika/hasła przy użyciu określonego mechanizmu nie powiodło się. Użytkownik nie jest uwierzytelniony.|  
|SamlInvalidSigningToken|Element SamlAssertion został podpisany przy użyciu tokenu, który nie został zweryfikowany zgodnie z protokołem. Jeśli używasz certyfikatów X. 509, sprawdź semantykę walidacji.|  
|TraceCodeSecurityServerSessionKeyUpdated|Klucz sesji zabezpieczeń został zaktualizowany przez serwer.|  
|TraceCodeSecurityServerSessionCloseReceived|Sesja zabezpieczeń serwera odebrała komunikat zamknięcia od klienta.|  
|SAMLAuthenticationStatementMissingSubject|W SamlAuthenticationStatement brakuje wymaganego SamlSubjectStatement.|  
|UnexpectedEndOfFile|Nieoczekiwany koniec pliku.|  
|UnsupportedAlgorithmForCryptoOperation|Określony algorytm nie jest obsługiwany dla określonej operacji.|  
|XmlLangAttributeMissing|Brak wymaganego atrybutu XML: lang.|  
|TraceCodeSecurityImpersonationSuccess|Personifikacja zabezpieczeń na serwerze zakończyła się pomyślnie.|  
|SAMLAuthorityBindingMissingLocationOnRead|Brak atrybutu "Location" dla odczytywanej elemencie SamlAuthorityBinding lub ma on długość 0.|  
|SAMLAttributeStatementMissingSubjectOnRead|Brak elementu "SamlSubject" dla SamlAttributeStatement.|  
|SAMLAuthorizationDecisionStatementMissingSubjectOnRead|Brak elementu "SamlSubject" dla odczytywanego SamlAuthorizationDecisionStatement.|  
|SAMLBadSchema|Podczas odczytywania elementu SamlAssertion ten określony element okazał się niezgodny ze schematem.|  
|SAMLAssertionIDIsInvalid|Określony element "assertionId" dla elementu SamlAssertion musi zaczynać się od litery lub "_".|  
|TraceCodeSecurityActiveServerSessionRemoved|Serwer został usunięty z aktywnej sesji zabezpieczeń.|  
|UnableToCreateKeyedHashAlgorithmFromSymmetricCrypto|Nie można utworzyć elementu keyedHashAlgorithm dla określonego algorytmu z określonego kryptografii symetrycznej.|  
|SAMLAuthenticationStatementMissingAuthenticationMethod|Wartość "bioSamlAuthenticationStatement" określona dla elementu {0} nie może mieć wartości null ani długości 0.|  
|TraceCodeSecurityImpersonationFailure|Personifikacja zabezpieczeń na serwerze nie powiodła się.|  
|Domyślne|(Domyślnie)|  
|UnsupportedNodeTypeInReader|Określony typ węzła o określonej nazwie nie jest obsługiwany.|
