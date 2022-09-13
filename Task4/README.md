# Introduction to Programming

## Assignment: Task 4

*This final task is challenging, and is intended for those
who want a challenge! It is possible to pass the module very well
without attempting this.*

### The Problem

A message has been received that appears to be encrypted. Our finest codebreakers have failed to decipher it.
A program is required that will automatically detect the encryption used, and will hence print the decrypted message.

### The Task

You have a file that contains a message that is encrypted (there are a few examples in the project repo). Your task is
to write a program that will decrypt the text.

Your program should be entirely self-contained. It should be provided with the name of the file containing the
encrypted text, and should then display the decrypt. Optionally, it could report that this is not possible, perhaps
because the text is not encrypted as suspected.

**There should be no user interaction.** 

It is strongly suspected that the message uses a simple Caesar cypher (i.e. the text is "shifted"). This means 
that it is susceptible to a brute-force attack, which is probably the best way to proceed.

*Note: If you want to try a different approach, such as frequency analysis, feel free!*

You can assume that the message is sufficiently long that a brute-force attack will succeed.

As a guide, the solution running below is about 85 lines long, formatted as per PEP-8. It uses one module of encryption
functions (35 lines) and another utility module (4 lines).

### Examples

The following illustrate what should happen when the program executes for the most obvious scenarios. The below 
samples are on Windows - the program should obviously work similarly on proper operating systems.

First, note that the program exits if the filename provided does not exist (or cannot be opened).

```text
$ py caesar_cracker.py missing.txt
Cannot open "missing.txt". Sorry about that.
```

Here is a message, encrypted.

```text
$ cat message.txt
Bc cbs kcizr vojs pszwsjsr wb hvs zogh msofg ct hvs bwbshssbhv qsbhifm hvoh
hvwg kcfzr kog pswbu kohqvsr yssbzm obr qzcgszm pm wbhszzwusbqsg ufsohsf
hvob aob'g obr msh og acfhoz og vwg ckb; hvoh og asb pigwsr hvsagszjsg opcih
hvswf jofwcig qcbqsfbg hvsm ksfs gqfihwbwgsr obr ghirwsr, dsfvodg ozacgh
og boffckzm og o aob kwhv o awqfcgqcds awuvh gqfihwbwgs hvs hfobgwsbh
qfsohifsg hvoh gkofa obr aizhwdzm wb o rfcd ct kohsf. Kwhv wbtwbwhs
qcadzoqsbqm asb ksbh hc obr tfc cjsf hvwg uzcps opcih hvswf zwhhzs ottowfg,
gsfsbs wb hvswf oggifobqs ct hvswf sadwfs cjsf aohhsf. Wh wg dcggwpzs
hvoh hvs wbtigcfwo ibrsf hvs awqfcgqcds rc hvs goas. Bc cbs uojs o hvciuvh
hc hvs czrsf kcfzrg ct gdoqs og gcifqsg ct viaob robusf, cf hvciuvh ct
hvsa cbzm hc rwgawgg hvs wrso ct zwts idcb hvsa og wadcggwpzs cf
wadfcpopzs. Wh wg qifwcig hc fsqozz gcas ct hvs asbhoz vopwhg ct hvcgs
rsdofhsr romg. Oh acgh hsffsghfwoz asb tobqwsr hvsfs awuvh ps chvsf asb
idcb Aofg, dsfvodg wbtsfwcf hc hvsagszjsg obr fsorm hc kszqcas o
awggwcbofm sbhsfdfwgs. Msh oqfcgg hvs uizt ct gdoqs, awbrg hvoh
ofs hc cif awbrg og cifg ofs hc hvcgs ct hvs psoghg hvoh dsfwgv,
wbhszzsqhg jogh obr qccz obr ibgmadohvshwq, fsuofrsr hvwg sofhv kwhv sbjwcig
smsg, obr gzckzm obr gifszm rfsk hvswf dzobg ouowbgh ig.
Obr sofzm wb hvs hksbhwshv qsbhifm qoas hvs ufsoh rwgwzzigwcbasbh.

```

Which can be automatically decrypted. Note that punctuation and line breaks are preserved.

```text
$ py caesar_cracker.py message.txt 
No one would have believed in the last years of the nineteenth century that
this world was being watched keenly and closely by intelligences greater
than man's and yet as mortal as his own; that as men busied themselves about
their various concerns they were scrutinised and studied, perhaps almost
as narrowly as a man with a microscope might scrutinise the transient
creatures that swarm and multiply in a drop of water. With infinite
complacency men went to and fro over this globe about their little affairs,
serene in their assurance of their empire over matter. It is possible
that the infusoria under the microscope do the same. No one gave a thought
to the older worlds of space as sources of human danger, or thought of
them only to dismiss the idea of life upon them as impossible or
improbable. It is curious to recall some of the mental habits of those
departed days. At most terrestrial men fancied there might be other men
upon Mars, perhaps inferior to themselves and ready to welcome a
missionary enterprise. Yet across the gulf of space, minds that
are to our minds as ours are to those of the beasts that perish,
intellects vast and cool and unsympathetic, regarded this earth with envious
eyes, and slowly and surely drew their plans against us.
And early in the twentieth century came the great disillusionment.

```

Efficiency is not really a concern here, but your program should display its output within a few seconds. 

Finally, if the program suspects that the message is not encrypted with a Caesar cypher it should say so! Here
is the result of feeding the decrypted message into the program:

```text 
$ py caesar_cracker.py eve.txt 
Cannot decrypt. Most likely not a Caesar Cypher at work here.
```
