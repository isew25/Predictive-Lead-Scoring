# Predictive-Lead-Scoring



### Problem Statement
X Education sells online courses to industry professionals. The company markets its courses on several websites and search engines like Google. Once these people land on the website, they might browse the courses or fill up a form for the course or watch some videos. When these people fill up a form providing their email address or phone number, they are classified to be a lead. Moreover, the company also gets leads through past referrals. Once these leads are acquired, employees from the sales team start making calls, writing emails, etc. Through this process, some of the leads get converted while most do not. The typical lead conversion rate at X education is around 30%.


### Business Goal
X Education needs help in selecting the most promising leads, i.e. the leads that are most likely to convert into paying customers. The company needs a model wherein you a lead score is assigned to each of the leads such that the customers with higher lead score have a higher conversion chance and the customers with lower lead score have a lower conversion chance. The CEO, in particular, has given a ballpark of the target lead conversion rate to be around 80%.


### Data Description
<table border=0 cellpadding=0 cellspacing=0 width=594 style='border-collapse:
 collapse;table-layout:fixed;width:447pt'>
 <col class=xl648560 width=123 style='mso-width-source:userset;mso-width-alt:
 4305;width:93pt'>
 <col class=xl638560 width=471 style='mso-width-source:userset;mso-width-alt:
 16453;width:354pt'>
 <tr height=21 style='height:15.5pt'>
  <td height=21 class=xl678560 width=123 style='height:15.5pt;width:93pt'>Variables</td>
  <td class=xl688560 width=471 style='border-left:none;width:354pt'>Description</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl668560 width=123 style='height:14.5pt;width:93pt'>Prospect
  ID</td>
  <td class=xl668560 width=471 style='border-left:none;width:354pt'>A unique ID
  with which the customer is identified.</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl658560 width=123 style='height:14.5pt;border-top:none;
  width:93pt'>Lead Number</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>A lead number assigned to each lead procured.</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>Lead Origin</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>The origin identifier with which the customer was identified to
  be a lead. Includes API, Landing Page Submission, etc.</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl658560 width=123 style='height:14.5pt;border-top:none;
  width:93pt'>Lead Source</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>The source of the lead. Includes Google, Organic Search, Olark
  Chat, etc.</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>Do Not Email</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>An indicator variable selected by the customer wherein they
  select whether of not they want to be emailed about the course or not.</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>Do Not Call</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>An indicator variable selected by the customer wherein they
  select whether of not they want to be called about the course or not.</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>Converted</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>The target variable. Indicates whether a lead has been
  successfully converted or not.</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl658560 width=123 style='height:14.5pt;border-top:none;
  width:93pt'>TotalVisits</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>The total number of visits made by the customer on the website.</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>Total Time Spent on Website</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>The total time spent by the customer on the website.</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>Page Views Per Visit</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>Average number of pages on the website viewed during the visits.</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>Last Activity</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>Last activity performed by the customer. Includes Email Opened,
  Olark Chat Conversation, etc.</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl658560 width=123 style='height:14.5pt;border-top:none;
  width:93pt'>Country</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>The country of the customer.</td>
 </tr>
 <tr height=58 style='height:43.5pt'>
  <td height=58 class=xl658560 width=123 style='height:43.5pt;border-top:none;
  width:93pt'>Specialization</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>The industry domain in which the customer worked before.
  Includes the level 'Select Specialization' which means the customer had not
  selected this option while filling the form.</td>
 </tr>
 <tr height=20 style='mso-height-source:userset;height:15.0pt'>
  <td height=20 class=xl658560 width=123 style='height:15.0pt;border-top:none;
  width:93pt'>How did you hear about X Education</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>The source from which the customer heard about X Education.</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>What is your current occupation</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>Indicates whether the customer is a student, umemployed or
  employed.</td>
 </tr>
 <tr height=77 style='height:58.0pt'>
  <td height=77 class=xl658560 width=123 style='height:58.0pt;border-top:none;
  width:93pt'>What matters most to you in choosing this course</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>An option selected by the customer indicating what is their main
  motto behind doing this course.</td>
 </tr>
 <tr height=40 style='mso-height-source:userset;height:30.0pt'>
  <td height=40 class=xl658560 width=123 style='height:30.0pt;border-top:none;
  width:93pt'>Search</td>
  <td rowspan=6 class=xl698560 width=471 style='border-bottom:.5pt solid black;
  border-top:none;width:354pt'>Indicating whether the customer had seen the ad
  in any of the listed items.</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl658560 width=123 style='height:14.5pt;border-top:none;
  width:93pt'>Magazine</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl658560 width=123 style='height:14.5pt;border-top:none;
  width:93pt'>Newspaper Article</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>X Education Forums</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl658560 width=123 style='height:14.5pt;border-top:none;
  width:93pt'>Newspaper</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>Digital Advertisement</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>Through Recommendations</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>Indicates whether the customer came in through recommendations.</td>
 </tr>
 <tr height=58 style='height:43.5pt'>
  <td height=58 class=xl658560 width=123 style='height:43.5pt;border-top:none;
  width:93pt'>Receive More Updates About Our Courses</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>Indicates whether the customer chose to receive more updates
  about the courses.</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl658560 width=123 style='height:14.5pt;border-top:none;
  width:93pt'>Tags</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>Tags assigned to customers indicating the current status of the
  lead.</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>Lead Quality</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>Indicates the quality of lead based on the data and intuition
  the the employee who has been assigned to the lead.</td>
 </tr>
 <tr height=58 style='height:43.5pt'>
  <td height=58 class=xl658560 width=123 style='height:43.5pt;border-top:none;
  width:93pt'>Update me on Supply Chain Content</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>Indicates whether the customer wants updates on the Supply Chain
  Content.</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>Get updates on DM Content</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>Indicates whether the customer wants updates on the DM Content.</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl658560 width=123 style='height:14.5pt;border-top:none;
  width:93pt'>Lead Profile</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>A lead level assigned to each customer based on their profile.</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl658560 width=123 style='height:14.5pt;border-top:none;
  width:93pt'>City</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>The city of the customer.</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>Asymmetrique Activity Index</td>
  <td rowspan=4 class=xl698560 width=471 style='border-bottom:.5pt solid black;
  border-top:none;width:354pt'>An index and score assigned to each customer
  based on their activity and their profile</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>Asymmetrique Profile Index</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>Asymmetrique Activity Score</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>Asymmetrique Profile Score</td>
 </tr>
 <tr height=58 style='height:43.5pt'>
  <td height=58 class=xl658560 width=123 style='height:43.5pt;border-top:none;
  width:93pt'>I agree to pay the amount through cheque</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>Indicates whether the customer has agreed to pay the amount
  through cheque or not.</td>
 </tr>
 <tr height=58 style='height:43.5pt'>
  <td height=58 class=xl658560 width=123 style='height:43.5pt;border-top:none;
  width:93pt'>a free copy of Mastering The Interview</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>Indicates whether the customer wants a free copy of 'Mastering
  the Interview' or not.</td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39 class=xl658560 width=123 style='height:29.0pt;border-top:none;
  width:93pt'>Last Notable Activity</td>
  <td class=xl658560 width=471 style='border-top:none;border-left:none;
  width:354pt'>The last notable acitivity performed by the student.</td>
 </tr>
 <![if supportMisalignedColumns]>
 <tr height=0 style='display:none'>
  <td width=123 style='width:93pt'></td>
  <td width=471 style='width:354pt'></td>
 </tr>
 <![endif]>
</table>
