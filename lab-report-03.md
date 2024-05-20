# Lab Report 3: Bugs and Commands (week 6)

---

## Part 1: Bugs
1. Failure inducing input for the Array reverseInPlace method
```
#Code
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = arr[arr.length - i - 1];
  }
}

@Test
public void testReverseInPlace1(){
  int[] inp1 = {0,2,4,6};
  ArrayExamples.reverseInPlace(inp1);
  assertArrayEquals(new int[]{6,4,2,0}, inp1);
}
```

2. Input which doesn't induce a failure

```
#Code
@Test
public testReversedMultple(){
  int[] input1 = {3};
  assertArrayEquals(new int[]{3}, ArrayExamples.reversed(input1);
}
```

3. The Symptom as a result of running the two tests above

 ![Image](https://github.com/Domenicj1/cse15l-lab-reports/assets/146692334/763c3f81-93cc-4501-924c-10977c520488)

4. The "After" code changes to fix the buggy behavior

```
#Code
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

Corrected Method

```
#Code
static void reverseInPlace(int[] arr) {
  if(arr.length > 0){
  for(int i = 0; i < arr.length; i += 1) {
    int temp = arr[i];
    arr[i] = arr[arr.length - i - 1];
    arr[arr.length - i - 1] = temp;
    }
  }
}
```

5. The fixed implementation correctly swaps elements in the array by iterating only halfway and swapping elements from opposite ends,
ensuring that each element is moved to its correct position exactly once. The buggy implementation, however, overwrites the elements
of the array without preserving their original values, resulting in an incorrect final state where only the elements from the second half
of the array are correctly reversed.

---

## Part 2: Researching Commands

The `grep` command (stands for Global Regular Expression Print) in Unix/Linux is a helpful tool for searching through files and directories for specific patterns;
used to search, match, then print the lines in a given file which appeal to the given text pattern. Here are four interseting and easy-to-use flags to enhace 
the usage of the `grep` command-line program:

1. `-i` (ignore case)
Description: This option makes the search or the text pattern case-insensative, which can be useful when you desrire to match text of the same content regarless of difference in case.
- Examples:
  ```
  #Code
  Domenics-Laptop:technical domenicj$ grep -i "whistleblowers" plos/pmed.0020281.txt
        Whistleblowers serve no function if they cannot tell their stories. The present story of
        In the lonely and, at times, discouraging world of whistleblowing, we whistleblowers are
  Domenics-Laptop:technical domenicj$ grep -i "clinic" plos/pmed.0020281.txt
        misrepresented pharmaceuticals; clinical research trial results that have been sequestered
  ```
    - For the above given examples of the `grep` command being used with the `-i` option the command matches with lines containing the string "whistelblowers" and "clinic", respectivley. The results have both upper and lower case versions of the string argued.

2. `-r` or `-R` (recursive search)
Description: This flag searches for the pattern recursively through directories. The -r and -R flags are often used interchangeably, though there can be slight differences in behavior in some implementations.
- Examples:
  ```
  #Code
  Domenics-Laptop:technical domenicj$ grep -r "prevented" ./government
  ./government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt:fees. Additional restrictions prevented our grantees from doing
  ./government/Env_Prot_Agen/multi102902.txt:while often a planning challenge, have not prevented installations
  ./government/Gen_Account_Office/d0269g.txt:Specifically, in fiscal year 2000, FPI prevented $9.5 million in
  ./government/Gen_Account_Office/Sept14-2002_d011070.txt:workload demands prevented them from being able to plan and manage
  ./government/Gen_Account_Office/og98024.txt:injuries and illnesses prevented per year. This reduction is
  ./government/Media/Oregon_Poor.txt:disorder since he was 10 months old. Rules prevented Head Start
  ./government/Media/Workers_aid_center.txt:be prevented through education.
  ./government/Media/Program_Lodges.txt:Romeo said the lawyers prevented 13 evictions, had two others
  ./government/Media/Farm_workers.txt:The laws require that farm workers be prevented from entering
  Domenics-Laptop:technical domenicj$ grep -R "evictions" ./government
  ./government/About_LSC/Special_report_to_congress.txt:custody and visitation rights, evictions, access to health care,
  ./government/About_LSC/Special_report_to_congress.txt:and visitation rights, evictions, access to health care,
  ./government/About_LSC/Special_report_to_congress.txt:custody and visitation rights, evictions, access to health care,
  ./government/About_LSC/commission_report.txt:evictions are often timed to coincide with brief absences, and may
  ./government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt:emergencies such as evictions and domestic violence, have access to
  ./government/About_LSC/State_Planning_Special_Report.txt:housing evictions.4 Another major reform of 1996 instituted a
  ./government/Media/Oregon_Poor.txt:evictions. Cases involving collection of wages, wrongful discharge,
  ./government/Media/Eviction_law.txt:evictions, which he estimated at one or two a year.
  ./government/Media/Lockyer_Warns.txt:domestic violence situations, evictions from their homes and other
  ./government/Media/Service_Agency.txt:Pine Tree is dealing with fewer evictions pending in Augusta
  ./government/Media/Service_Agency.txt:"We specialize in public benefits, housing evictions and
  ./government/Media/residents_sue_city.txt:Development Act by having Raimondi carry out the evictions.
  ./government/Media/Legal_Aid_Society.txt:Prevented or forestalled 112 evictions, saving shelter costs of
  ./government/Media/Program_Lodges.txt:Romeo said the lawyers prevented 13 evictions, had two others
  ./government/Media/Program_Lodges.txt:Seventeen evictions were delayed, giving families additional
  ./government/Media/Legal_services_for_poor.txt:areas such as family law, consumer fraud, housing evictions and
  ```
  - For the above given examples of the `grep` command being used with the `-r` and `-R` option the relative paths show us the the terminal is recursivley starting from the argued `./government` subdirectory and going into all the underlying subdirectories to match all lines matching the argued strings.

3. `-l` (files with matches)
Description: This flag outputs only the names of files that contain the matching pattern. It is useful when you are interested in finding out which files contain the pattern rather than the exact lines.
- Examples:
```
#Code
Domenics-Laptop:technical domenicj$ grep -l "physical therapy" ./biomed/*.txt
./biomed/1471-2431-2-4.txt
./biomed/1472-6882-3-1.txt
./biomed/1472-6882-3-3.txt
./biomed/1472-6963-3-11.txt
Domenics-Laptop:technical domenicj$ grep -l "biomedical" ./biomed/*.txt
./biomed/1471-2105-3-16.txt
./biomed/1471-2105-3-17.txt
./biomed/1471-2164-3-7.txt
./biomed/1472-6807-1-1.txt
./biomed/1472-6882-1-12.txt
./biomed/1472-6882-3-3.txt
./biomed/1472-6920-2-3.txt
./biomed/1472-6947-3-5.txt
./biomed/1472-6947-3-8.txt
./biomed/1475-9276-1-3.txt
./biomed/1477-7827-1-54.txt
./biomed/gb-2001-2-4-research0012.txt
./biomed/gb-2003-4-4-r28.txt
./biomed/gb-2003-4-7-r46.txt
```
  - For the above given examples of the `grep` command being used with the `-l` option the relative paths to the text files containing the argued strings are printed to standard output rather than the actual lines with the strings themselves.

4. `-n` (line number)
Description: This flag prefixes each matching line with its line number in the file. It helps in identifying the exact location of the match.
- Examples:
```
#Code
Domenics-Laptop:technical domenicj$ grep -n "the commander" ./911report/*.txt
./911report/chapter-1.txt:604:    At 9:48, a representative from the White House shelter asked if there were any indications of another hijacked aircraft. The deputy director for operations mentioned the Delta flight and concluded that "that would be the fourth possible hijack." At 9:49, the commander of NORAD directed all air sovereignty aircraft to battle stations, fully armed.
./911report/chapter-1.txt:702:    General David Wherley-the commander of the 113th Wing-reached out to the Secret Service after hearing secondhand reports that it wanted fighters airborne. A Secret Service agent had a phone in each ear, one connected to Wherley and the other to a fellow agent at the White House, relaying instructions that the White House agent said he was getting from the Vice President. The guidance for Wherley was to send up the aircraft, with orders to protect the White House and take out any aircraft that threatened the Capitol. General Wherley translated this in military terms to flying "weapons free"-that is, the decision to shoot rests in the cockpit, or in this case in the cockpit of the lead pilot. He passed these instructions to the pilots that launched at 10:42 and afterward.
./911report/chapter-13.1.txt:255:                    Center, the head of the FBI's Counterterrorism Division, the commanders of the
./911report/chapter-13.4.txt:2892:                2003. KSM does acknowlNOTES TO CHAPTER 7 525 edge that the commander of al Faruq
./911report/chapter-3.txt:1105:                three of the helicopters, and the commander ordered the mission aborted. But
./911report/chapter-3.txt:1701:                Marine General Anthony Zinni, the commander in chief of the U.S. Central Command,
./911report/chapter-3.txt:1761:                tribals hold Bin Ladin captive for so long, and the commander of Joint Special
./911report/chapter-3.txt:1919:                evidence that the commanders were at the facilities.
./911report/chapter-9.txt:932:            Unlike the commanders in the North Tower, the senior chief in the lobby and the
Domenics-Laptop:technical domenicj$ grep -n "the helicopter" ./911report/*.txt
./911report/chapter-13.5.txt:1521:            64. For the helicopters' dispatch, see NYPD records, "Aviation Unit Flight Data
./911report/chapter-13.5.txt:1528:                Sept. 11, 2001. For the helicopters' subsequent actions and protocol, see NYPD
./911report/chapter-13.5.txt:1866:                2004). For the helicopter's perspective, see NYPD recordings, City Wide 1 and
./911report/chapter-13.5.txt:1868:                the helicopter not hovering, see NYPD interview 12, Aviation (Mar. 10, 2004). For
./911report/chapter-3.txt:1105:                three of the helicopters, and the commander ordered the mission aborted. But
./911report/chapter-9.txt:1130:                roof of either tower. At about 9:30, one of the helicopters present advised that a
```
  - For the above given examples of the `grep` command being used with the `-n` option, the terminal is printing to standar output lines which contain teh argued string in addition to telling us what specific line number each one is in for their relative files. 
