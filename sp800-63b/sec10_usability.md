<a name="sec10"></a>

<div class="breaker"></div>

## 10. Usability Considerations

_This section is informative._

[ISO/IEC 9241-11](#ISO9241-11) defines usability as the "extent to which a product can be used by specified users to achieve specified goals with effectiveness, efficiency and satisfaction in a specified context of use." This definition focuses on users, goals, and context of use as key elements necessary for achieving effectiveness, efficiency and satisfaction. A holistic approach considering these key elements is necessary to achieve usability. 

A user’s goal for accessing an information system is to perform an intended task; authentication is the task that enables this goal. As such, users benefit most when authentication is designed and implemented to make it easy to do the right thing, hard to do the wrong thing, and easy to recover when something goes wrong. 

Organizations should be cognizant of their stakeholders’ digital authentication ecosystem’s overall implications. Users often employ one or more authenticator, each for a different RP; then, they struggle to remember passwords, to recall which authenticator goes with which RP, and to carry multiple authentication devices. Evaluating authentication’s usability is critical, as poor usability often results in coping mechanisms and unintended work-arounds, which can ultimately degrade the intended security controls. 

To address users’ authentication needs and organizations’ security goals, assess the impact of usability across digital systems as part of the risk assessment when deciding on the Authenticator Assurance Level (AAL) requirements. If authenticators with a higher AAL offer better usability, allow their use for lower AAL applications. 

To achieve enhanced usability in authenticator selection, consider the combination of users, goals, use context, authenticator and the security risk assessment. This section takes this holistic view in applying usability principles to authenticators across their lifecycle. 

##### ASSUMPTIONS  

In this section, the term “users” means “Claimants” or “Subscribers.”

Guidelines and considerations are described from the end-users’ perspective. 
 
Accessibility and usability differ significantly; therefore, accessibility is out of scope for this section. Accessibility can be addressed in an organization’s implementation plans.

Leveraging a federation for authentication can allieviate many of the usability issues, though such an approach has its own tradeoffs, as discussed in NIST [SP 800-63C](#800-63C), _Federation and Assertions_.

### 10.1. Usability Considerations by Authenticator Type  
For selecting and implementing an authentication system, consider usability across the entire lifecycle of the selected authenticator(s) (i.e., enrollment and distribution, typical use, and intermittent events), while being mindful of the combination of users, their goals, and use context. This section discusses the usability considerations and implementation options for authenticators’ typical use and intermittent events. 
 
A single authenticator option generally does not suffice for the entire user population. Therefore, whenever possible (depending on the AAL requirements), provide alternative authenticator types and allow users to choose based on their needs. Task immediacy, a cost benefit analysis, or unfamiliarity with certain authenticators often impact choice. Users generally choose options that incur the least burden or cost at that moment; if a task requires immediate access to an information system, a user may prefer to create a new account and password rather than select an authenticator requiring more steps. Alternatively, users may choose a federated identity option (approved at the appropriate AAL) if they already have an account with an identity provider. Users may understand some authenticators better than others, and have different levels of trust based on their understanding. 
 
This section provides general usability considerations and possible implementations, but does not recommend specific solutions: the implementations mentioned are examples to encourage innovative technological approaches to address specific usability needs. Furthermore, usability considerations and their implementation solutions are sensitive to dependencies (including context of use) that prevent a one-size-fits-all solution. For example, a font size that works in the desktop computing environment may force text to scroll off of a small OTP device screen. Performing a usability evaluation on the selected authenticator is a critical component of implementation; it’s important to conduct evaluations with representative users, realistic goals and tasks, and appropriate use contexts. 
 
Positive user authentication experience is integral to the success of an organizations’ security posture. Therefore, strive to consider authenticators from the users’ perspective. The overarching authentication usability goal is to minimize user burden and authentication friction (the number of times a user has to authenticate, the steps involved, and the amount of information he or she has to track). Single sign-on exemplifies one such minimization strategy.

Usability considerations for typical usage of each authenticator type include:

*  Availability of the authenticator.
*  Users remember or have their authenticator readily available. 
*  Whenever possible (depending on the AAL requirements), provide users alternative authentication options. This allows users to choose based on their context, goals, and tasks (e.g., the frequency and immediacy of the task). Alternative authentication options will help address availability issues with the authenticator. 
*  Characteristics of user-facing text.
*  Write user-facing text (e.g., instructions, prompts, notifications, error messages) in plain language for the intended audience. Avoid the technical jargon and write for a 6th to 8th grade literacy level.
*  Consider the legibility of user-facing and user-entered text, including font style, size, color, and contrast with surrounding background. Font legibility is important because users have different levels of visual acuity and illegible text contributes to user entry errors. Legibility considerations include:
*  The highest contrast is black on white.
*  Sans serif fonts are easier to read. 
*  It’s beneficial to use fonts that clearly distinguish between easily confusable characters (such as the capital letter “O” and the number “0”).
*  User experience during authenticator entry.
*  Offer the option to display text during entry, as masked text entry is error-prone. Once the character is displayed long enough for the user to see, it can be hidden. Consider the device when determining masking delay time, as it takes longer to enter memorized secrets on mobile devices (such as tablets and smartphones) than on traditional desktop computers. 
*  Ensure the time allowed for text entry is adequate (i.e., the entry screen does not time out prematurely).
*  Provide clear, meaningful and actionable feedback on entry errors to reduce user confusion and frustration. Significant usability implications arise when users do not know they have entered text incorrectly. Take care to not provide so much detail in this feedback as to render the memorized secret vulnerable. 
*  Allow at least 10 entry attempts. 
*  Provide clear, meaningful feedback on number of remaining allowed attempts. For rate limiting (throttling), inform users how long they have to wait until the next attempt to reduce confusion and frustration.
*	  Depending on the implementation, consider form-factor constraints as they are particularly problematic when users must enter text on mobile devices. Providing larger touch areas will improve usability for entering memorized secrets on mobile devices.

To prevent users from needing to reauthenticate due to user inactivity, prompt users to show activity just before (e.g., 2 minutes before) the inactivity timeout would otherwise occur.

Clearly communicate how and where to acquire technical assistance at every stage of the process. For example, provide users information—such as a link to online self-service feature, chat sessions and a phone number for help desk support. Ideally, sufficient information is provided to enable users to recover from intermittent events on their own without outside intervention.

#### 10.1.1. Summary of Usability Considerations  
 
[Table 10-1](#t10-1) summarizes the usability considerations for typical usage and intermittent events for each of the eight authenticators. The sections following the table provide more detailed discussion on each authenticator. Many of the usability considerations for typical usage apply to most of the authenticator types, as demonstrated in the rows. The table highlights common and divergent usability characteristics across the authenticator types. Each column allows readers to easily identify the usability attributes to address for each authenticator. Depending on their goals and use context, users may value certain usability attributes over others. Whenever possible, provide alternative authenticator types and allow users to choose between them. 
It is important to note that multi-factor authenticators also inherit their secondary factor’s usability considerations. As biometrics are only allowed as an activation factor in multi-factor authentication solutions, usability considerations for biometrics are not included in Table 1 and are discussed in section 10.2.

<a name="t10-1"></a>
<div class="text-center" markdown="1">
![](sp800-63b/media/use.png)

**Table 10-1 Usability Considerations Summary by Authenticator Types**
</div>

#### 10.1.2. Memorized Secret  

**_Typical Usage_**  

Users manually input the memorized secret (commonly referred to as a password or PIN). 

Usability considerations for typical usage include:  

*  Availability of the memorized secret.
	*  The likelihood of recall failure increases as there are more items for users to remember; with fewer memorized secrets, users can more easily recall the specific memorized secret needed for a particular RP. The memory burden is greater for a less frequently used password.
	*  Whenever possible (depending on the AAL requirements), provide users with alternative authentication options. This allows users to choose based on their context, goals, and tasks (e.g., the frequency and immediacy of the task). Alternative authentication options will help address availability issues (e.g., when users cannot recall their memorized secrets). 

*  Characteristics of user-facing text.
	*  When possible, depending on device size, use a minimum font size of 12 points. 

*  User experience during entry of the memorized secret.
	*  Fields for entering memorized secrets support copy and paste functionality and memorized secrets of at least 64 characters in length; this allows the use of passphrases if desired. 

**_Intermittent Events_**  

Intermittent events with memorized secrets include, but are not limited to, reauthentication; account lock-out; throttling; number of allowed attempts exceeded; expired memorized secrets; and revocation. Additionally, users may proactively change their memorized secrets. 

Usability considerations for intermittent events include:  

*  When memorized secrets are used at AAL 2 or AAL 3, prompt users with adequate time (e.g., 1 hour) to save their work before the reauthentication event required at least once every 12 hours, regardless of user activity.
*  Provisions to create and change memorized secrets. 
	*  Clearly communicate information on how to create and change memorized secrets. 
	*  Simplify memorized secret policies by implementing technical defenses, including implementing approved encryption, storing memorized secrets in a form that is resistant to offline attacks, and using blacklists (see Section 5.1.1 for details).
		*  Clearly communicate memorized secret requirements, such as the minimum length of 8 characters (as specified in Section 5.1.1).
		*  Allow at least 64 characters in length to support the use of passphrases. Encourage users make memorized secrets as lengthy as they want, using any characters they like (including spaces), thus aiding passphrase memorization. 
		*  Do not impose other composition (complexity) rules (e.g. mixtures of different character types) on memorized secrets.
		*  Do not require that memorized secrets are changed arbitrarily (e.g., periodically) unless there is evidence of authenticator compromise or a user request. (Section 5.1.1)
	*  When creating memorized secrets, do not ask users to provide specific types of information (e.g., “What is your favorite food?”, “What was the name of your first pet?”). Such questions are difficult to remember, especially since personal preferences can change over time. 
	*  Provide clear, meaningful and actionable feedback when chosen passwords are rejected by online services (e.g., when it appears on a “black list” of unacceptable passwords or has been used previously used). Advise the user that they need to select a different secret because their previous choice was commonly used.
	
#### 10.1.3. Look-up Secrets  

**_Typical Usage_**

Users use the authenticator (physical or electronic record) to look up the appropriate secret(s) needed to respond to a verifier’s prompt. For example, a user may be asked to provide a specific subset of the numeric or character strings printed on a card in table format.

Usability considerations for typical usage include:  

*  User experience during entry of look-up secrets.
	*  Consider the prompts’ complexity and size. The larger the subset of secrets a user is prompted to look up, the greater the usability implications are, both the cognitive workload and physical difficulty during entry. 

**_Intermittent Events_**

Intermittent events with look-up secrets include, but are not limited to: reauthentication; account lock-out; throttling; number of allowed attempts exceeded; damaged, lost, or stolen look-up secret authenticator; expired look-up secrets; and revocation.

Usability considerations for intermittent events include:

*  When look-up secrets are used at AAL 2, prompt users with adequate time (e.g., 1 hour) to save their work prior to the mandatory reauthentication event required at least once every 12 hours, regardless of user activity.

#### 10.1.4. Out of Band

**_Typical Usage_**

Out of band authentication requires users have access to a primary and secondary communication channel. 

Usability considerations for typical usage:
 
*  Depending on the implementation, the following are additional usability considerations for implementers:
	*  Notify users of the receipt of an authentication secret on a locked device. However, if the user locked the out of band device, the user will need to authenticate to the device to access the authentication secret (since the authentication secret cannot be displayed on a locked device screen). 
	*  Depending on the implementation, consider form-factor constraints as they are particularly problematic when users must enter text on mobile devices. Providing larger touch areas will improve usability for entering memorized secrets on mobile devices.
		*  A better usability option is to offer features that do not require text entry on mobile devices (e.g., a single tap on the screen, or a copy feature so users can copy and paste the out of band secrets). 
*  Providing users such features is particularly helpful when the primary and secondary channels are on the same device. For example, it is difficult for users to transfer the authentication secret on a smartphone because they must switch back and forth—potentially multiple times—between the out of band application and the primary channel. 

**_Intermittent Events_**

Intermittent events with out of band devices include, but are not limited to: reauthentication; account lock-out; throttling; authentication secret not received; number of allowed attempts exceeded; damaged, lost, or stolen out of band devices; and revocation. Additionally, users often change or upgrade their mobile devices, necessitating updating the linkage between the primary and secondary channels.

Usability considerations for intermittent events include:  

*  When out of band is used at AAL 2, prompt users with adequate time (e.g., 1 hour) to save their work before the reauthentication event required at least once every 12 hours, regardless of user activity.

#### 10.1.5. Single Factor OTP Device  

**_Typical Usage_**  

Users access the one-time password generated by the single-factor OTP device. The authenticator output is typically displayed on the device and the user enters it for the verifier, although direct electronic output from the device as input to a computer is also allowed. 

Usability considerations for typical usage include:  

*  Authenticator output allows at least one minute between changes, but ideally allows users the full 2 minutes as specified in the requirement that the nonce be changed at least once every 2 minutes. Users need adequate time to enter the authenticator output (including looking back and forth between the single-factor OTP device and the entry screen).
*  Depending on the implementation, the following are additional usability considerations for implementers: 
	*  If the single-factor OTP device supplies its output via an electronic interface such as USB, this is preferable since users do not have to manually enter the authenticator output. However, if a physical input (such as pressing a button) is required to operate, the location of the USB ports could pose usability difficulties. For example, the USB ports of some computers are located on the back of the computer and will be difficult for users to reach.
		*  Limited availability of a direct computer interface such as a USB port could pose usability difficulties. For example, the number of USB ports on laptop computers is often very limited; this may force users to unplug other USB peripherals in order to use the single-factor OTP device. 

**_Intermittent Events_**  

Intermittent events with single-factor OTP devices include, but are not limited to: reauthentication; account lock-out; throttling; number of allowed attempts exceeded; damaged, lost, or stolen single-factor OTP devices; and revocation. 

Usability considerations for intermittent events include:  

*  When single-factor OTP devices are used at AAL 2, prompt users with adequate time (e.g., 1 hour) to save their work before the reauthentication event required at least once every 12 hours, regardless of user activity.

#### 10.1.6. Multi-Factor OTP Device  

**_Typical Usage_**  

Users access the authenticator output (i.e., one-time password) generated by the multi-factor OTP device that requires activation through a second authentication factor. The authenticator output is typically displayed on the device and the user manually enters it for the verifier, although direct electronic output from the device as input to a computer is also allowed. The second authentication factor may be achieved through some kind of integral entry pad to enter a memorized secret, an integral biometric (e.g., fingerprint) reader or a direct computer interface (e.g., USB port). Usability considerations for the additional factor apply as well (see section 10.1.2 for Memorized Secrets and section 10.2 for Biometrics used in Multi-Factor Authenticators). 

Usability considerations for typical usage include:  

*  User experience during manual entry of authenticator output.
	*  Ensure the time allowed for entry of authenticator output is commensurate with the length and complexity of the authenticator output (e.g., the entry screen does not time out prematurely).
		*  Authenticator output allows at least one minute between changes, but ideally allows users the full 2 minutes as specified in the requirement that the nonce be changed at least once every 2 minutes. Users need adequate time to enter the authenticator output (including looking back and forth between the multi-factor OTP device and the entry screen).
*  Depending on the implementation, the following are additional usability considerations for implementers:
	*  Consider form-factor constraints if users must unlock the multi-factor OTP device via an integral entry pad or enter the authenticator output on mobile devices. Typing on small devices is significantly more error prone and time-consuming than typing on a traditional keyboard. The smaller the integral entry pad and onscreen keyboard, the more difficult it is to type. Providing larger touch areas improves usability for unlocking the multi-factor OTP device or entering the authenticator output on mobile devices.
	*  Limited availability of a direct computer interface like a USB port could pose usability difficulties. For example, laptop computers often have a limited number of USB ports, which may force users to unplug other USB peripherals to use the multi-factor OTP device. 
	
**_Intermittent Events_**  

Intermittent events with multi-factor OTP devices include, but are not limited to: reauthentication; account lock-out; throttling; number of allowed attempts exceeded (for either factor); damaged, lost, or stolen multi-factor OTP devices; and revocation. 

Usability considerations for intermittent events include:  

*  When multi-factor OTP devices are used at AAL 2 or AAL 3, prompt users with adequate time (e.g., 1 hour) to save their work before the reauthentication event required at least once every 12 hours, regardless of user activity.

#### 10.1.7. Single Factor Cryptographic Device  

**_Typical Usage_**
Users authenticate by proving possession of the single-factor cryptographic device. 

Usability considerations for typical usage include:  

*  Depending on the implementation, the following are additional usability considerations for implementers:
	*  Requiring a physical input (such as pressing a button) to operate the single-factor cryptographic device could pose usability difficulties. For example, some USB ports are located on the back of computers, making it difficult for users to reach. 
		*  Limited availability of a direct computer interface like a USB port could pose usability difficulties. For example, laptop computers often have a limited number of USB ports, which may force users to unplug other USB peripherals to use the single-factor cryptographic device. 
		

**_Intermittent Events_**  

Intermittent events with single-factor cryptographic devices include, but are not limited to: reauthentication; damaged, lost, or stolen single-factor cryptographic devices; and revocation. 

Usability considerations for intermittent events include:  

*  When single-factor cryptographic devices are used at AAL 2 or AAL 3 , prompt users with adequate time (e.g., 1 hour) to save their work before the reauthentication event required at least once every 12 hours, regardless of user activity.

#### 10.1.8. Multi-Factor Cryptographic Software   

**_Typical Usage_**  

In order to authenticate, users prove possession and control of the cryptographic key stored on disk or some other “soft” media that requires activation. The activation is through the input of a second authentication factor, either a memorized secret or a biometric; usability considerations for the additional factor apply as well (see section 10.1.2 for Memorized Secrets and section 10.2 for Biometrics used in Multi-Factor Authenticators). 

Usability considerations for typical usage include:  

*  Depending on the implementation, the following are additional usability considerations for implementers:
	*  Give cryptographic keys appropriately descriptive names that are meaningful to users since users have to recognize and recall which cryptographic key to use for which authentication task. This prevents users from having to deal with multiple similarly and ambiguously named cryptographic keys. Selecting from multiple cryptographic keys on smaller mobile devices (such as smartphones) may be particularly problematic if the names of the cryptographic keys are shortened due to reduced screen size.
	
**_Intermittent Events_**  

Intermittent events with multi-factor cryptographic software include, but are not limited to: reauthentication; account lock-out; number of allowed attempts exceeded; non-functional multi-factor cryptographic software; and revocation. 

Usability considerations for intermittent events include:  

*  When multi-factor cryptographic software is used at AAL 2, prompt users with adequate time (e.g., 1 hour) to save their work before the reauthentication event required at least once every 12 hours, regardless of user activity.

#### 10.1.9. Multi-Factor Cryptographic Device  

**_Typical Usage_**  

Users authenticate by proving possession of the multi-factor cryptographic device and control of the protected cryptographic key. The device is activated by a second authentication factor, either a memorized secret or a biometric; usability considerations for the additional factor apply as well (see section 10.1.2 for Memorized Secrets and section 10.2 for Biometrics used in Multi-Factor Authenticators).

Usability considerations for typical usage include:

*  Depending on the implementation, the following are additional usability considerations for implementers:
	*  Ideally, the multi-factor cryptographic devices does not require a hardware connection to use. However, if using a hardware connection, the multi-factor cryptographic device does not require users to keep the device connected. Users may forget to disconnect the multi-factor cryptographic device when they are done with it (such as forgetting a smartcard in the smartcard reader and walking away from the computer).
		*  Users need to be informed regarding whether the multi-factor cryptographic device is required to stay connected or not. 
	*  Give cryptographic keys appropriately descriptive names that are meaningful to users since users have to recognize and recall which cryptographic key to use for which authentication task. This prevents users being faced with multiple similarly and ambiguously named cryptographic keys. Selecting from multiple cryptographic keys on smaller mobile devices (such as smartphones) may be particularly problematic if the names of the cryptographic keys are shortened due to reduced screen size.
	*  Limited availability of a direct computer interface like a USB port could pose usability difficulties. For example, laptop computers often have a limited number of USB ports, which may force users to unplug other USB peripherals to use the multi-factor cryptographic device. 

**_Intermittent Events_**  

Intermittent events with multi-factor cryptographic devices include, but are not limited to: reauthentication; account lock-out; throttling; number of allowed attempts exceeded; damaged, lost, or stolen multi-factor cryptographic devices; and revocation.

Usability considerations for intermittent events include:  

*  When multi-factor cryptographic devices are used at AAL 2 or AAL 3, prompt users with adequate time (e.g., 1 hour) to save their work before the reauthentication event required at least once every 12 hours, regardless of user activity.

### 10.2. Biometrics Usability Considerations   

This section provides a high-level overview of biometrics general usability considerations. For a more detailed discussion of biometric usability, see Usability & Biometrics, Ensuring Successful Biometric Systems, <http://www.nist.gov/customcf/get_pdf.cfm?pub_id=152184>.

Although there are other biometric modalities, the following three biometric modalities are more commonly used for authentication: fingerprint, face, and iris. 

**_Typical Usage_**  

*  For all modalities, user familiarity and practice with the device improves performance. 
*  Device affordances (properties that allow a user to perform an action), feedback, and clear instructions are critical to a user’s success with the biometric device. For example, provide clear instructions on the required actions for liveness detection.
*  Ideally, users can select the modality they are most comfortable with for their second authentication factor. The user population may be more comfortable with—and accepting of—some biometric modalities than others. 
*  User experience with biometrics as an activation factor.
	*  Allow at least 10 attempts. 
	*  Provide clear, meaningful feedback on number of remaining allowed attempts. For example, for rate limiting (throttling), inform users of the time period they have to wait until next attempt to reduce user confusion and frustration. 
*  Fingerprint Usability Considerations:
	*  Users have to remember which finger(s) they used for initial enrollment.
	*  The amount of moisture on the finger(s) affects the sensor’s ability for successful capture.
	*  Additional factors influencing fingerprint capture quality include age, gender, and occupation (e.g., users handling chemicals or working extensively with their hands may have degraded friction ridges). 
*  Face Usability Considerations:
	*  Users have to remember whether they wore any artifacts, such as glasses, during enrollment because it affects facial recognition accuracy.
	*  Differences in environmental lighting conditions can affect facial recognition accuracy.
	*  Facial poses affect facial recognition accuracy (e.g., smiling versus neutral expression).
*  Iris Usability Considerations:
	*  Users wearing colored contacts may affect the iris recognition accuracy. 
	*  Users who have had eye surgery may need to re-enroll post-surgery.
	*  Differences in environmental lighting conditions can affect iris recognition accuracy, especially for certain iris colors. 

**_Intermittent Events_**  

As biometrics are only permitted as a second factor for multi-factor authentication, usability considerations for intermittent events with the primary factor still apply. Intermittent events with biometrics use include, but are not limited to, the following, which may affect recognition accuracy:  

*  If a user injures his/her enrolled finger(s), fingerprint recognition may not work. Fingerprint authentication will be difficult for users with degraded fingerprints. 
*  The time elapsed between the time of facial recognition for authentication and the time of the initial enrollment can affect recognition accuracy as a user’s face changes naturally over time. A user’s weight changes (e.g., weight gain or loss) may also be a factor.
*  Iris recognition may not work for people who had eye surgery, unless they re-enroll. 

Across all biometric modalities, usability considerations for intermittent events include:  

*  An alternative authentication method must be available and functioning. In cases where biometrics do not work, allow users to use a memorized secret as an alternative second factor.
*  Provisions for technical assistance.
	*  Inform users of factors that may affect the sensitivity of the biometric sensor (e.g., cleanliness of the sensor).