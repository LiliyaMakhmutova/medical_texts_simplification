# Appendix of Automated Medical Text Simplification for Enhanced Patient Access
## Examples for Principles of Medical Text Simplification

### Congruence:
#### Example 1
Original:

``HISTORY OF PRESENT ILLNESS: The patient is a 61-year-old white female status post right total knee replacement secondary to degenerative joint disease performed by Dr. A at ABCD Hospital on 08/21/2007.``

Simplification 1 (much important information is lost):

``Story: A 61-year-old woman had surgery on her right knee on 08/21/2007 because of joint disease.``

Simplification 2 (important information is preserved, though it is partially simplified for a better understanding):

``HISTORY OF PRESENT ILLNESS: The patient is a 61-year-old white woman after right total knee replacement because of the chronic process of wear and tear on the joint performed by Dr. A at ABCD Hospital on 08/21/2007.``

So here, is the full definition of [degenerative joint disease](https://www.aapmr.org/about-physiatry/conditions-treatments/pain-neuromuscular-medicine-rehabilitation/degenerative-joint-disease):
>Degenerative joint disease, also known as osteoarthritis (OA), is a common “wear and tear” disease. The underlying cause of this condition is typically chronic repetitive motion that results in inflammation and structural joint damage. Inflammation causes pain, >redness, and swelling. The tiniest amount of trauma triggers inflammation as the body attempts to clean up/protect damaged tissue. This cycle of joint damage and inflammation leads to the breakdown of cartilage that serves as a smooth gliding surface and cushion in the >joints.  Any joint can be affected, but frequently found in the knees, hands, hips, and spine. 

#### Example 2
Original:

``COURSE: CRP 1.2 (elevated), ESR 10, RF 20, ANA 1:40, ANCA <1:40, TSH 2.0, FT4 1.73, Anticardiolipin antibody IgM 10.8GPL units (normal <10.9), Anticardiolipin antibody IgG 14.8GPL (normal<22.9), SSA and SSB were normal.``

Simplification 1 (much information is lost and there is a conclusion that everything is relatively fine):

``The person's blood tests showed some elevated levels, but nothing too concerning.``

Good simplification:

``COURSE: C-reactive protein test to check inflammation in the body showed 1.2 (elevated).
An erythrocyte sedimentation rate (ESR) test that measures how quickly red blood cells settle to the bottom of a test tube was 10. 
This test can also show if inflammation is present in the body.
Rheumatoid factor (RF) test result was 20. 
An RF test is often used to help diagnose rheumatoid arthritis and other autoimmune disorders.
ANA and ANCA tests are used to help diagnose autoimmune disorders too. 
The value for ANA was 1:40. 
The value for ANCA was less than 1:40. 
SSA and SSB tests were normal.
These tests are also used to check autoimmune conditions.
To find out how well the thyroid is working, TSH and FT4 tests were also conducted. 
The value for TSH was 2.0, and for FT4 it was 1.73. 
To check for abnormal blood clots, Anticardiolipin antibody (both IgM and IgG) tests were conducted. 
For IgM, the value was 10.8 GPL units (while normal should be less than 10.9).
For IgG, the value was 14.8 GPL units (while normal should be less than 22.9).``


### Simplicity

Original:

``The stomach was transilluminated and an optimal position for the PEG tube was identified using the single poke method.``

Possible simplification:

``The tube with light and camera was put in the stomach and the best position for the feeding tube was identified and the light on it from inside was directed to outside. The light could be seen from the outside, and a finger was pressed against the abdominal wall where the light was located so that the indentation was seen on the camera.``


## Manual Evaluation
### Positive ChatGPT's features

- ChatGPT's abbreviations disclosure abilities

  Example 1:  
  Original:
  ``EXAM: BP150/79, HR77, RR22, 37.4C.``  
  ChatGPT:
  ``PHYSICAL: Blood pressure is 150/79, heart rate is 77, breathing rate is 22, and temperature is 37.4C.``
  
  Example 2:       
  Original:
  ``CN: VFFTC, Pupils 5/5 decreasing to 3/3.``  
  ChatGPT:
  ``CRANIAL NERVES: Vision, facial expression, hearing, and taste are working fine. Her pupils react to light, but the right pupil is smaller.``
  
  Here ``CN`` abbreviation may be ambiguously disclosed as ``Clinic Nurse``, ``Cavernous Nerve``, ``Child Nutrition`` or ``Cranial Nerves``. However, ChatGPT was able to choose the correct one depending on the context. 

- ChatGPT's rewriting abilities
  
  Example 1:  
  Original:
  ``The mucosa throughout the colon and in the terminal ileum was normal, with no evidence of colitis.``  
  ChatGPT:
  ``The inner lining of the colon and small intestine looked normal, and there were no signs of inflammation.``
  
  Example 2:   
  Original
  ``Some purulent material could be expressed through the opening.``  
  ChatGPT:
  ``Some pus-like material could be seen coming out of the opening.``


### Problems that were found in ChatGPT's medical text simplification

- ChatGPT produces abstracts or summarizations rather than simplification:
  
  ``51-57) A test called cerebral angiography showed evidence of blood vessel inflammation, which may be causing the brain changes.``

- ChatGPT makes up facts. 

  Example 1:
  
  Original:
  ``Oral contrast was also administered.``
  
  ChatGPT:
  ``They also made you drink some liquid.``
  
  There is no evidence that liquid oral contrast is used (it can also be in the form of tablets). However, ChatGPT outputs that it was liquid.


  Example 2:
  
  Original:
  ``A 12-mm simple cyst is present in the inferior pole of the right kidney.``
  
  ChatGPT:
  ``There's a small 12-mm liquid-filled bump in the lower part of the right kidney.``
  
  ChatGPT is adding its judgment that, moreover, may be untrue (as in some cases a kidney cyst of size 12 mm may be considered to be big).  

  Example 3:
  
  Original:
  ``CI (BPD/OFD): (70-86) 86. 
  FL/HC: (19.2-20.8) 17.1.
  HC/AC: (1.05-1.21) 1.5.``
    
  ChatGPT:
  ``The ratio of head size to face size is 86, which is within the expected range (70-86).
  The ratio of leg bone length to head circumference is 17.1, which is within the expected range (19.2-20.8).
  The ratio of head circumference to abdomen size is 1.5, which is within the expected range (1.05-1.21).``
  ChatGPT contradicts its output as 17.1 doesn’t lie within \[19.2,20.8\] interval and 1.5 doesn’t lie in \[1.05,1.21\], however, 86 is in the 70-86 range.


- ChatGPT somehow lacks commonsense reasoning or medical ""knowledge"". 

  Example 1.
  
  It can be seen that though the abbreviations were disclosed correctly, ChatGPT lacks some medical or common sense knowledge. Here a test of pupils' response to the light is tested by exposing the light and measuring pupils' shrinkage. So, one measurement is related to light exposure (3/3, both eyes were of size 3 during light exposure), and another one is related to pupils' size in a dimmed light (5/5, both eyes were of size 5 in a dimmed light). And ``VFFTC"" suggests that no visual defects were found. However, ChatGPT concluded that ``3" is a measurement of the left eye and ``5" is the measurement of the right one (which suggests abnormality contradicting ``VFFTC""). 
  
  Original:
  ``CN: VFFTC, Pupils 5/5 decreasing to 3/3.``
        
  ChatGPT:
  ``CRANIAL NERVES: Vision, facial expression, hearing, and taste are working fine. Her pupils react to light, but the right pupil is smaller.``
  
  Example 2.
  
  Using ``one hole"" ChatGPT probably simplifies ``single poke"" without taking into account a context. Of course, there may be only a single poke with a needle, but at this stage, it is more related to a procedure of finding a good place for tube installation using ``poke'' of a finger.
  
  Original:
  ``The stomach was transilluminated and an optimal position for the PEG tube was identified using the single poke method.``
        
  ChatGPT:
  ``They shone a light through the stomach and found the best place to put the tube using a method that only needed one hole.`
  
  Human:
  ``The tube with light and camera was put in the stomach and the best position for the feeding tube was identified and the light on it from inside was directed to outside. The light could be seen from the outside, and a finger was pressed against the abdominal wall where the light was located so that the indentation was seen on the camera.``
  


- ChatGPT may omit important facts or oversimplify. 
  Example 1.
  
  Much important information is left out, including the patient's race (``white""), surgery details (instead of ``right total knee replacement"" we got ``surgery on her right knee"") disease details (``degenerative""), doctor's name (``Dr. A''), and the name of the hospital (``ABCD Hospital'').
  
  Original:
  ``HISTORY OF PRESENT ILLNESS: The patient is a 61-year-old white female status post right total knee replacement secondary to degenerative joint disease performed by Dr. A at ABCD Hospital on 08/21/2007.``
  
  ChatGPT:
  ``Story: A 61-year-old woman had surgery on her right knee on 08/21/2007 because of joint disease.``
     
  Example 2.
  
  Here ""problems"" may be considered oversimplification. Of course, any person would have some problems after a serious surgery, but some problems are expected given the situation and some problems are related to badly performed surgery. So, meaning is not fully preserved.
  
  Original:
  ``COMPLICATIONS: None.``
        
  ChatGPT:
  ``There were no problems during or after the surgery.``
  
  Example 3. 
  We can point out that the bases of the lungs are just a part of the lungs that is visible on CT images while scanning the belly and pelvis, and it doesn’t mean that the whole lungs are normal.
  
  Original:
  ``The lung bases are clear.``
        
  ChatGPT:
  ``Your lungs look fine.``

- ChatGPT is biased towards rewriting a text by any means, even if it has been already quite simple.
  
  Example 1. 
  We can see that although the original text is quite accessible, ChatGPT still changed it.
  
  Original:
  ``This is a 22-year-old pregnant female.``
        
  ChatGPT:
  ``A 22-year-old woman who is pregnant.``
  
  Example 2. 
  Here we can see that the word ``about'' was added, which may sound like the doctors measured the amount of the liquid by a rule of thumb rather than exactly. 

  Original:
  ``Total of 100 mL of Isovue was administered intravenously.``
        
  ChatGPT:
  ``Liquid called Isovue was put into a vein, about 100 mL in total.``
  
  Example 3. 
  Another example illustrates that ChatGPT tends to produce more personal sentences. It uses ""Your"" though the sentence was originally impersonal. Another thing that can be noted is that ""lower back spine"" sounds tautological. \\

  Original:
  ``Degenerative changes are present in the lumbar spine.``
            
  ChatGPT:
  ``Your lower back spine shows signs of wear and tear.``



- ChatGPT sometimes uses words such as ""a"", ""about"", ""some"", ""called"", rather than properly simplify a concept or explain. It also frequently outputs undersimplifications.
  
  Example 1. 
  
  Original:
  ``The Bolster was placed on the PEG site.``
  
  ChatGPT:
  ``They placed a thing called a Bolster on the PEG site.``
  
  Example 2. 
  
  Original:
  ``Cerebral palsy.``
    
  ChatGPT:
  ``A condition called cerebral palsy.``
  
  
  Let's now have a look at undersimplification examples. 
    
  Example 1. 
  In the first case, ""diverticulitis"" is not simplified at all. 
  
  Original:
  ``There is evidence of focal wall thickening in the sigmoid colon (image #69) with adjacent fat stranding in association with a diverticulum.``
  
  ChatGPT:
  ``In one part of the colon, the wall seems thicker in the picture (#69), and there's some fat around a pocket, which could mean diverticulitis.``
  
  Example 2. 
  In the other example, the ""placenta"" and ""cervix"" are not simplified.   
  
  Original:
  ``Placenta: Posterior without evidence of placenta previa.``
  
  ChatGPT:
  ``The placenta is located in the back and is not blocking the cervix.``

