
<xml xmlns="https://developers.google.com/blockly/xml" is_dbot="true" collection="false">
  <variables>
    <variable id="x]b3MHpbtR?cJQDP@,eG">martingale:resultIsWin</variable>
    <variable id="[M$5RsD`g|8-P;C+mbf4">martingale:profit</variable>
    <variable id="3^~61:59m?#VJ(:SG^^[">setMaxStake?</variable>
    <variable id="]6T=O624:eVRioXro1kh">Notification:currentStake</variable>
    <variable id="Kb@{Vb{+5IqV=d~y*dcr">martingale:totalProfit</variable>
    <variable id="6G^6o^Ic@rjF|sHv*m.6">martingale:tradeAgain</variable>
    <variable id="4vh+dtelQS#?}@cNPcN!">maxStake</variable>
    <variable id="*p5|Lkk9Q^ZuPBQ-48g2">martingale:profitThreshold</variable>
    <variable id="FRbI:RhI/`[lrO`o;=P,">martingale:multiplier</variable>
    <variable id="[$B]vBH,~wrN`PUt5m/f">martingale:initialStake</variable>
    <variable id="a1BTYNHC?_yR4sfvNJ7N">martingale:lossThreshold</variable>
    <variable id="p#@Pr/Y.sKueWX#oRSPl">Notification:totalProfit</variable>
    <variable id="ipD5?_dQ1Zkvf%v|[?DQ">martingale:size</variable>
    <variable id="I--KAm(C+#{d?~ip*23e">Notification:profitThresholdReached</variable>
    <variable id="5SwcMzq.f)VNUzjbKfrw">Notification:lossThresholdReached</variable>
  </variables>
  <block type="trade_definition" id="i]`fLRZ]?mshi{9kS+fg" deletable="false" x="-79" y="-49">
    <statement name="TRADE_OPTIONS">
      <block type="trade_definition_market" id="w2tV#|N1PqTM)~5-6|An" deletable="false" movable="false">
        <field name="MARKET_LIST">synthetic_index</field>
        <field name="SUBMARKET_LIST">random_daily</field>
        <field name="SYMBOL_LIST">RDBEAR</field>
        <next>
          <block type="trade_definition_tradetype" id="4BIa?F@i2*Mlrd:{G,SF" deletable="false" movable="false">
            <field name="TRADETYPECAT_LIST">callput</field>
            <field name="TRADETYPE_LIST">callput</field>
            <next>
              <block type="trade_definition_contracttype" id="kujUv]]-mtF@Na3q/.(g" deletable="false" movable="false">
                <field name="TYPE_LIST">both</field>
                <next>
                  <block type="trade_definition_candleinterval" id="[DsSG;O7*n`fK%ed;aj5" deletable="false" movable="false">
                    <field name="CANDLEINTERVAL_LIST">60</field>
                    <next>
                      <block type="trade_definition_restartbuysell" id="]RX]Y0mfW-(HKGjkY]ly" deletable="false" movable="false">
                        <field name="TIME_MACHINE_ENABLED">TRUE</field>
                        <next>
                          <block type="trade_definition_restartonerror" id="il/#yt1#I,KbD:6BQx?#" deletable="false" movable="false">
                            <field name="RESTARTONERROR">TRUE</field>
                          </block>
                        </next>
                      </block>
                    </next>
                  </block>
                </next>
              </block>
            </next>
          </block>
        </next>
      </block>
    </statement>
    <statement name="INITIALIZATION">
      <block type="variables_set" id="qKO~.`hPZgl;YZp+5Gov">
        <field name="VAR" id="3^~61:59m?#VJ(:SG^^[">setMaxStake?</field>
        <value name="VALUE">
          <block type="logic_boolean" id="niiMS4+%T9)/K%DABd7.">
            <field name="BOOL">TRUE</field>
          </block>
        </value>
        <next>
          <block type="variables_set" id="-jDR^266z(Nid-G$WXhp">
            <field name="VAR" id="4vh+dtelQS#?}@cNPcN!">maxStake</field>
            <value name="VALUE">
              <shadow type="math_number" id="M}AkH@%CQb}X2|.-+^W%">
                <field name="NUM">1</field>
              </shadow>
            </value>
          </block>
        </next>
      </block>
    </statement>
    <statement name="SUBMARKET">
      <block type="trade_definition_tradeoptions" id="8=uN{72G(CSbw2LN=h?0">
        <mutation xmlns="http://www.w3.org/1999/xhtml" has_first_barrier="false" has_second_barrier="false" has_prediction="false"></mutation>
        <field name="DURATIONTYPE_LIST">s</field>
        <value name="DURATION">
          <shadow type="math_number" id="1K)d0!)#tPQO5TUe{xfh">
            <field name="NUM">30</field>
          </shadow>
        </value>
        <value name="AMOUNT">
          <shadow type="math_number" id="N(D?4f-m6;UOK|gD~v[s">
            <field name="NUM">1</field>
          </shadow>
          <block type="procedures_callreturn" id="JKIgKdNnmR8J;^];~[kp">
            <mutation xmlns="http://www.w3.org/1999/xhtml" name="Martingale Trade Amount"></mutation>
            <data>x3TA)`V~gtD7?rqNj[.9</data>
          </block>
        </value>
      </block>
    </statement>
  </block>
  <block type="after_purchase" id="cb%w4#L|)A]1F1+)uk_u" x="812" y="110">
    <statement name="AFTERPURCHASE_STACK">
      <block type="controls_if" id="Y7vVfZ`@dP+KBKXW6C|a">
        <value name="IF0">
          <block type="procedures_callreturn" id="_ES]wQc*K9uQmJ1a:MA,">
            <mutation xmlns="http://www.w3.org/1999/xhtml" name="Martingale Trade Again After Purchase">
              <arg name="martingale:profit"></arg>
              <arg name="martingale:resultIsWin"></arg>
            </mutation>
            <data>N,_%hZ47`]!eOyc7%u8]</data>
            <value name="ARG0">
              <block type="read_details" id="6~ERQr:ogkONG,..Ooj+">
                <field name="DETAIL_INDEX">4</field>
              </block>
            </value>
            <value name="ARG1">
              <block type="contract_check_result" id="N85;,Dl!TJMa_U[tgj6#">
                <field name="CHECK_RESULT">win</field>
              </block>
            </value>
          </block>
        </value>
        <statement name="DO0">
          <block type="trade_again" id="(T~B6mBGK5D2unsjU25_"></block>
        </statement>
      </block>
    </statement>
  </block>
  <block type="before_purchase" id="Z])37`R^9KsrX4I7bAqP" deletable="false" x="0" y="824">
    <statement name="BEFOREPURCHASE_STACK">
      <block type="purchase" id="?QH{0D:/t^fpgu}4sb`x">
        <field name="PURCHASE_LIST">PUT</field>
      </block>
    </statement>
  </block>
  <block type="procedures_defnoreturn" id="s`u(+vlS44fI;pul:nfW" collapsed="true" x="0" y="1000">
    <mutation xmlns="http://www.w3.org/1999/xhtml">
      <arg name="martingale:resultIsWin" varid="x]b3MHpbtR?cJQDP@,eG"></arg>
    </mutation>
    <field name="NAME">Martingale Core Functionality</field>
    <comment pinned="false" h="80" w="160">Describe this function...</comment>
    <statement name="STACK">
      <block type="text_join" id="%BiEW1gsT2[%D%90GC3P">
        <field name="VARIABLE" id="]6T=O624:eVRioXro1kh">Notification:currentStake</field>
        <statement name="STACK">
          <block type="text_statement" id="Hj|vILSUt]aB|IP?*ado">
            <value name="TEXT">
              <shadow type="text" id="JS0_3T=Sb0}+w:YzZiK9">
                <field name="TEXT">Current stake:</field>
              </shadow>
            </value>
            <next>
              <block type="text_statement" id="gxd{k4]yB:C+Z39AwkJT">
                <value name="TEXT">
                  <shadow type="text" id="dX8[ROI1Z%vv|Vb##q.d">
                    <field name="TEXT"></field>
                  </shadow>
                  <block type="procedures_callreturn" id="QtD^/]l{G1Jj}%h]k|^i">
                    <mutation xmlns="http://www.w3.org/1999/xhtml" name="Martingale Trade Amount"></mutation>
                    <data>x3TA)`V~gtD7?rqNj[.9</data>
                  </block>
                </value>
              </block>
            </next>
          </block>
        </statement>
        <next>
          <block type="notify" id="X?l1])Y7!^m1aVJ$qnjS">
            <field name="NOTIFICATION_TYPE">warn</field>
            <field name="NOTIFICATION_SOUND">silent</field>
            <value name="MESSAGE">
              <shadow type="text" id="PRTfr2+|kgnz/i5{j~Z?">
                <field name="TEXT">abc</field>
              </shadow>
              <block type="variables_get" id="(kmzO*5N^X`^3uvRT9}+">
                <field name="VAR" id="]6T=O624:eVRioXro1kh">Notification:currentStake</field>
              </block>
            </value>
            <next>
              <block type="controls_if" id="B-,mWt$U5Ox.^T5l[AU)">
                <mutation xmlns="http://www.w3.org/1999/xhtml" else="1"></mutation>
                <value name="IF0">
                  <block type="variables_get" id="LKMXXjt~M8@Xs?F,2_mg">
                    <field name="VAR" id="x]b3MHpbtR?cJQDP@,eG">martingale:resultIsWin</field>
                  </block>
                </value>
                <statement name="DO0">
                  <block type="variables_set" id="o`/I0!/s^K{7$xZtceYh">
                    <field name="VAR" id="FRbI:RhI/`[lrO`o;=P,">martingale:multiplier</field>
                    <value name="VALUE">
                      <shadow type="math_number" id="#{5k!r3Zgo@m8VSv[fPn">
                        <field name="NUM">1</field>
                      </shadow>
                    </value>
                  </block>
                </statement>
                <statement name="ELSE">
                  <block type="variables_set" id="DA78AxndLk]Q@dIBt7O|">
                    <field name="VAR" id="FRbI:RhI/`[lrO`o;=P,">martingale:multiplier</field>
                    <value name="VALUE">
                      <block type="math_arithmetic" id="YzC3]lEc(!m8!NK/T/^0">
                        <field name="OP">MULTIPLY</field>
                        <value name="A">
                          <shadow type="math_number" id="5D$Yu+XV{_7(tTs-imu.">
                            <field name="NUM">1</field>
                          </shadow>
                          <block type="variables_get" id="1q-nik8DE5Q2,h$gg}f6">
                            <field name="VAR" id="FRbI:RhI/`[lrO`o;=P,">martingale:multiplier</field>
                          </block>
                        </value>
                        <value name="B">
                          <shadow type="math_number" id="#Om$-j0C[l$EXD$2JdKl">
                            <field name="NUM">2</field>
                          </shadow>
                          <block type="variables_get" id="OIfB4l~Tv5_$I;ILt79^">
                            <field name="VAR" id="ipD5?_dQ1Zkvf%v|[?DQ">martingale:size</field>
                          </block>
                        </value>
                      </block>
                    </value>
                    <next>
                      <block type="controls_if" id="yq2aWWPfZo9BqwmM^gp,">
                        <value name="IF0">
                          <block type="logic_operation" id="P:vAy5mETFAlR6416JW@">
                            <field name="OP">AND</field>
                            <value name="A">
                              <block type="variables_get" id="UTgA6uy4MgDFQ[tbq=v2">
                                <field name="VAR" id="3^~61:59m?#VJ(:SG^^[">setMaxStake?</field>
                              </block>
                            </value>
                            <value name="B">
                              <block type="logic_compare" id="WI3(qR{d}7zdoDevLGVx">
                                <field name="OP">GT</field>
                                <value name="A">
                                  <block type="procedures_callreturn" id="Zt-ad5[w(|?#4g,A*Ze,">
                                    <mutation xmlns="http://www.w3.org/1999/xhtml" name="Martingale Trade Amount"></mutation>
                                    <data>x3TA)`V~gtD7?rqNj[.9</data>
                                  </block>
                                </value>
                                <value name="B">
                                  <block type="variables_get" id="z;Utrvg*JkBzz{cf)SYV">
                                    <field name="VAR" id="4vh+dtelQS#?}@cNPcN!">maxStake</field>
                                  </block>
                                </value>
                              </block>
                            </value>
                          </block>
                        </value>
                        <statement name="DO0">
                          <block type="variables_set" id="ca;U5I#KW?1eJ;^[H2Ji">
                            <field name="VAR" id="FRbI:RhI/`[lrO`o;=P,">martingale:multiplier</field>
                            <value name="VALUE">
                              <shadow type="math_number" id="p1`qUx`N_;V{kY*mLXW$">
                                <field name="NUM">1</field>
                              </shadow>
                            </value>
                            <next>
                              <block type="notify" id="xBU}6LWyNZWbGStkUOKw">
                                <field name="NOTIFICATION_TYPE">error</field>
                                <field name="NOTIFICATION_SOUND">silent</field>
                                <value name="MESSAGE">
                                  <shadow type="text" id="Du/t4#rzavkWBAW.z#oN">
                                    <field name="TEXT">Stake resets for the next trade (reason: exceeds max stake amount)</field>
                                  </shadow>
                                </value>
                              </block>
                            </next>
                          </block>
                        </statement>
                      </block>
                    </next>
                  </block>
                </statement>
              </block>
            </next>
          </block>
        </next>
      </block>
    </statement>
  </block>
  <block type="procedures_defreturn" id="x3TA)`V~gtD7?rqNj[.9" collapsed="true" x="0" y="1096">
    <field name="NAME">Martingale Trade Amount</field>
    <comment pinned="false" h="80" w="160">Describe this function...</comment>
    <statement name="STACK">
      <block type="controls_if" id="m|NvCXT=!Z{`Uz`r:m|$">
        <value name="IF0">
          <block type="logic_compare" id="PeeDP94E)V=#S~69%:Hk">
            <field name="OP">EQ</field>
            <value name="A">
              <block type="variables_get" id="f.km2[vh(%]*F2SuNU%G">
                <field name="VAR" id="*p5|Lkk9Q^ZuPBQ-48g2">martingale:profitThreshold</field>
              </block>
            </value>
            <value name="B">
              <block type="logic_null" id="[R@rhEZMD*U(Q~m#KCMh"></block>
            </value>
          </block>
        </value>
        <statement name="DO0">
          <block type="variables_set" id="{}-XA:3=]2W.Aq|zIiP(">
            <field name="VAR" id="*p5|Lkk9Q^ZuPBQ-48g2">martingale:profitThreshold</field>
            <value name="VALUE">
              <shadow type="math_number" id="3.I$vEnsexC5u.Rpi:D*">
                <field name="NUM">50</field>
              </shadow>
            </value>
          </block>
        </statement>
        <next>
          <block type="controls_if" id="Usu?ety_d{DdqDPFw78m">
            <value name="IF0">
              <block type="logic_compare" id="e8qk^*j@H6ng{H8}Vv3R">
                <field name="OP">EQ</field>
                <value name="A">
                  <block type="variables_get" id="EzMg)v,zllQlN8mb?5{h">
                    <field name="VAR" id="a1BTYNHC?_yR4sfvNJ7N">martingale:lossThreshold</field>
                  </block>
                </value>
                <value name="B">
                  <block type="logic_null" id=")k{fUEt[/)H?^NgdHT*+"></block>
                </value>
              </block>
            </value>
            <statement name="DO0">
              <block type="variables_set" id=":OS%IuonU;AkRO!H-SEF">
                <field name="VAR" id="a1BTYNHC?_yR4sfvNJ7N">martingale:lossThreshold</field>
                <value name="VALUE">
                  <shadow type="math_number" id="jFUuG0iQN6)ZBPfCdQLQ">
                    <field name="NUM">10</field>
                  </shadow>
                </value>
              </block>
            </statement>
            <next>
              <block type="controls_if" id="-XkmG`TcfQ120.%uPetQ">
                <value name="IF0">
                  <block type="logic_compare" id="N_[iwyYPZsj8rKmV:GTj">
                    <field name="OP">EQ</field>
                    <value name="A">
                      <block type="variables_get" id="{:C[v0vezVot0F{#8z#C">
                        <field name="VAR" id="[$B]vBH,~wrN`PUt5m/f">martingale:initialStake</field>
                      </block>
                    </value>
                    <value name="B">
                      <block type="logic_null" id="n{-TB11IDQw5O(9-=zIr"></block>
                    </value>
                  </block>
                </value>
                <statement name="DO0">
                  <block type="variables_set" id="BEp45H17VcN)bNjaC13X">
                    <field name="VAR" id="[$B]vBH,~wrN`PUt5m/f">martingale:initialStake</field>
                    <value name="VALUE">
                      <shadow type="math_number" id="}+aGJ1X=IcU%J.-atf/b">
                        <field name="NUM">1</field>
                      </shadow>
                    </value>
                  </block>
                </statement>
                <next>
                  <block type="controls_if" id="!_^Y3:=rFtL6aF0#~DFT">
                    <value name="IF0">
                      <block type="logic_compare" id="cmU^7GLDMN~++3mP^+$n">
                        <field name="OP">EQ</field>
                        <value name="A">
                          <block type="variables_get" id="?:}:mXzQgsbYRfm~0C*H">
                            <field name="VAR" id="ipD5?_dQ1Zkvf%v|[?DQ">martingale:size</field>
                          </block>
                        </value>
                        <value name="B">
                          <block type="logic_null" id="$fhp;`t^Ie,SzUO{y4qg"></block>
                        </value>
                      </block>
                    </value>
                    <statement name="DO0">
                      <block type="variables_set" id="-93lGY=!6I#8sh)~z`3Z">
                        <field name="VAR" id="ipD5?_dQ1Zkvf%v|[?DQ">martingale:size</field>
                        <value name="VALUE">
                          <shadow type="math_number" id="L%t[38C3CxJ35M6*!(^A">
                            <field name="NUM">2</field>
                          </shadow>
                        </value>
                      </block>
                    </statement>
                    <next>
                      <block type="controls_if" id="D?v;;-QQ=]k/%a8XK/RQ">
                        <value name="IF0">
                          <block type="logic_compare" id="@LNL@pA9b#8SJGe$4zur">
                            <field name="OP">EQ</field>
                            <value name="A">
                              <block type="variables_get" id="Wc7riq/+8b5q+,f9@uR6">
                                <field name="VAR" id="FRbI:RhI/`[lrO`o;=P,">martingale:multiplier</field>
                              </block>
                            </value>
                            <value name="B">
                              <block type="logic_null" id="g^$2zUmo/#v.0SthN[lG"></block>
                            </value>
                          </block>
                        </value>
                        <statement name="DO0">
                          <block type="variables_set" id="ZA0SX,/mZR=Q@Qs{0-nM">
                            <field name="VAR" id="FRbI:RhI/`[lrO`o;=P,">martingale:multiplier</field>
                            <value name="VALUE">
                              <shadow type="math_number" id="y^=8[fZs0weMPlUMzJ0v">
                                <field name="NUM">1</field>
                              </shadow>
                            </value>
                          </block>
                        </statement>
                        <next>
                          <block type="controls_if" id="$8xAQGgiV1U|3nDiZ0:X">
                            <value name="IF0">
                              <block type="logic_compare" id="]TOR9VFmHAS3vC~A20mf">
                                <field name="OP">EQ</field>
                                <value name="A">
                                  <block type="variables_get" id="]esY#,FN9C}bbgG:As`K">
                                    <field name="VAR" id="Kb@{Vb{+5IqV=d~y*dcr">martingale:totalProfit</field>
                                  </block>
                                </value>
                                <value name="B">
                                  <block type="logic_null" id="0NIH0U%Bk-4w*SgA+dX|"></block>
                                </value>
                              </block>
                            </value>
                            <statement name="DO0">
                              <block type="variables_set" id="2s+YXTZv%VGRY=?APf^h">
                                <field name="VAR" id="Kb@{Vb{+5IqV=d~y*dcr">martingale:totalProfit</field>
                                <value name="VALUE">
                                  <shadow type="math_number" id="%JgI()#r0Zu#ruzKLXpj">
                                    <field name="NUM">0</field>
                                  </shadow>
                                </value>
                              </block>
                            </statement>
                          </block>
                        </next>
                      </block>
                    </next>
                  </block>
                </next>
              </block>
            </next>
          </block>
        </next>
      </block>
    </statement>
    <value name="RETURN">
      <block type="math_arithmetic" id="MR,#W3HBlh/CZGh.TF:m">
        <field name="OP">MULTIPLY</field>
        <value name="A">
          <shadow type="math_number" id="r@Ex,Lui|v*G9_/K}hxx">
            <field name="NUM">1</field>
          </shadow>
          <block type="variables_get" id="DnN;77BHT-uqtZY4%{Z/">
            <field name="VAR" id="FRbI:RhI/`[lrO`o;=P,">martingale:multiplier</field>
          </block>
        </value>
        <value name="B">
          <shadow type="math_number" id="d|m/YvXVLv}7m5`iwU[d">
            <field name="NUM">1</field>
          </shadow>
          <block type="variables_get" id="w$Dd.MXXRvJmyJuC~XUu">
            <field name="VAR" id="[$B]vBH,~wrN`PUt5m/f">martingale:initialStake</field>
          </block>
        </value>
      </block>
    </value>
  </block>
  <block type="procedures_defreturn" id="N,_%hZ47`]!eOyc7%u8]" collapsed="true" x="0" y="1192">
    <mutation xmlns="http://www.w3.org/1999/xhtml">
      <arg name="martingale:profit" varid="[M$5RsD`g|8-P;C+mbf4"></arg>
      <arg name="martingale:resultIsWin" varid="x]b3MHpbtR?cJQDP@,eG"></arg>
    </mutation>
    <field name="NAME">Martingale Trade Again After Purchase</field>
    <comment pinned="false" h="80" w="160">Describe this function...</comment>
    <statement name="STACK">
      <block type="math_change" id="G)p)~Q+g*Hsak%Mg_PMd">
        <field name="VAR" id="Kb@{Vb{+5IqV=d~y*dcr">martingale:totalProfit</field>
        <value name="DELTA">
          <shadow type="math_number" id="f3#]0d{vTsn{rHX(5}u.">
            <field name="NUM">1</field>
          </shadow>
          <block type="variables_get" id="|xO6#sg$RRE9Ub8W6Oq=">
            <field name="VAR" id="[M$5RsD`g|8-P;C+mbf4">martingale:profit</field>
          </block>
        </value>
        <next>
          <block type="variables_set" id="p?gdu**|cGlmOTw^G_D@">
            <field name="VAR" id="Kb@{Vb{+5IqV=d~y*dcr">martingale:totalProfit</field>
            <value name="VALUE">
              <block type="math_arithmetic" id="lSSFZC-1xm}v~a9_Xw3@">
                <field name="OP">DIVIDE</field>
                <value name="A">
                  <shadow type="math_number" id=".5qAFI5)LT=5YVv[zeo1">
                    <field name="NUM">1</field>
                  </shadow>
                  <block type="math_round" id="qe@`Q7,j_0|sTdj`,F|B">
                    <field name="OP">ROUND</field>
                    <value name="NUM">
                      <shadow type="math_number" id="0K3%a`,T:^3?IEGCk0z^">
                        <field name="NUM">3.1</field>
                      </shadow>
                      <block type="math_arithmetic" id="9b({-h28~_/qs:s!*WkN">
                        <field name="OP">MULTIPLY</field>
                        <value name="A">
                          <shadow type="math_number" id="~ROA+z|O84V#W?m^-)@.">
                            <field name="NUM">1</field>
                          </shadow>
                          <block type="variables_get" id="`n%c*E0(V,0.I[D%,s!j">
                            <field name="VAR" id="Kb@{Vb{+5IqV=d~y*dcr">martingale:totalProfit</field>
                          </block>
                        </value>
                        <value name="B">
                          <shadow type="math_number" id="9_(K(Vo5-U%*h=jJ]+oF">
                            <field name="NUM">100</field>
                          </shadow>
                        </value>
                      </block>
                    </value>
                  </block>
                </value>
                <value name="B">
                  <shadow type="math_number" id="bRV]-C*:i*}p+`XB_rv7">
                    <field name="NUM">100</field>
                  </shadow>
                </value>
              </block>
            </value>
            <next>
              <block type="procedures_callnoreturn" id=".HOK{2j(GR=qlV..gc}o">
                <mutation xmlns="http://www.w3.org/1999/xhtml" name="Martingale Core Functionality">
                  <arg name="martingale:resultIsWin"></arg>
                </mutation>
                <data>s`u(+vlS44fI;pul:nfW</data>
                <value name="ARG0">
                  <block type="variables_get" id="pgjZvSeFe;B(ZL|$v(!:">
                    <field name="VAR" id="x]b3MHpbtR?cJQDP@,eG">martingale:resultIsWin</field>
                  </block>
                </value>
                <next>
                  <block type="text_join" id="jW!]JTxnzDnsTxu^+gT!">
                    <field name="VARIABLE" id="p#@Pr/Y.sKueWX#oRSPl">Notification:totalProfit</field>
                    <statement name="STACK">
                      <block type="text_statement" id="Y3$$Wh@Fr:}*_(hMrtvA">
                        <value name="TEXT">
                          <shadow type="text" id="Hm%lX3B[OAyV1OrSBqCn">
                            <field name="TEXT">Total Profit:</field>
                          </shadow>
                        </value>
                        <next>
                          <block type="text_statement" id="[(J[NV?+P0O}]:cG4cP}">
                            <value name="TEXT">
                              <shadow type="text" id="ku6fI!hhZEVk5TXISI?=">
                                <field name="TEXT"></field>
                              </shadow>
                              <block type="variables_get" id="FUazlkQi-clh,Vt%{Z2@">
                                <field name="VAR" id="Kb@{Vb{+5IqV=d~y*dcr">martingale:totalProfit</field>
                              </block>
                            </value>
                          </block>
                        </next>
                      </block>
                    </statement>
                    <next>
                      <block type="notify" id="e$Pci.r)?[2i9=/L]hI{">
                        <field name="NOTIFICATION_TYPE">info</field>
                        <field name="NOTIFICATION_SOUND">silent</field>
                        <value name="MESSAGE">
                          <shadow type="text" id="7q`k_em:FgUT1=*tkVFH">
                            <field name="TEXT">abc</field>
                          </shadow>
                          <block type="variables_get" id="!EEfy=FF,cmavRcMOd`9">
                            <field name="VAR" id="p#@Pr/Y.sKueWX#oRSPl">Notification:totalProfit</field>
                          </block>
                        </value>
                        <next>
                          <block type="variables_set" id="TPOGTMEqW41Wa{D|?]`V">
                            <field name="VAR" id="6G^6o^Ic@rjF|sHv*m.6">martingale:tradeAgain</field>
                            <value name="VALUE">
                              <block type="logic_boolean" id="WK=zt|fDEnw}@@bsZ+%v">
                                <field name="BOOL">FALSE</field>
                              </block>
                            </value>
                            <next>
                              <block type="controls_if" id="KTuC8HMyaDp6Q3xId0@A">
                                <mutation xmlns="http://www.w3.org/1999/xhtml" else="1"></mutation>
                                <value name="IF0">
                                  <block type="logic_compare" id="7[;$pQigi:R:T3}s(G6^">
                                    <field name="OP">LT</field>
                                    <value name="A">
                                      <block type="variables_get" id="{T)uCW@]IoOpTp7;JdSO">
                                        <field name="VAR" id="Kb@{Vb{+5IqV=d~y*dcr">martingale:totalProfit</field>
                                      </block>
                                    </value>
                                    <value name="B">
                                      <block type="variables_get" id="5m`a=f+P*-wT*3b-Acg=">
                                        <field name="VAR" id="*p5|Lkk9Q^ZuPBQ-48g2">martingale:profitThreshold</field>
                                      </block>
                                    </value>
                                  </block>
                                </value>
                                <statement name="DO0">
                                  <block type="controls_if" id=".O}[W@YXqN#zGd%ewXJ*">
                                    <mutation xmlns="http://www.w3.org/1999/xhtml" else="1"></mutation>
                                    <value name="IF0">
                                      <block type="logic_compare" id="%XaSru*P96b@:s~*f6/b">
                                        <field name="OP">GT</field>
                                        <value name="A">
                                          <block type="variables_get" id=".j^jS`B22${#0xP~J7;S">
                                            <field name="VAR" id="Kb@{Vb{+5IqV=d~y*dcr">martingale:totalProfit</field>
                                          </block>
                                        </value>
                                        <value name="B">
                                          <block type="math_single" id="K9$ftop.bUpkoibNkVQL">
                                            <field name="OP">NEG</field>
                                            <value name="NUM">
                                              <shadow type="math_number" id="il+Ggh=KS*zx`bo34Q$x">
                                                <field name="NUM">9</field>
                                              </shadow>
                                              <block type="variables_get" id="`nfV$q=C}%gf{r$Jyt-#">
                                                <field name="VAR" id="a1BTYNHC?_yR4sfvNJ7N">martingale:lossThreshold</field>
                                              </block>
                                            </value>
                                          </block>
                                        </value>
                                      </block>
                                    </value>
                                    <statement name="DO0">
                                      <block type="variables_set" id="b_=Q.Dj-VBXKcWz33ioo">
                                        <field name="VAR" id="6G^6o^Ic@rjF|sHv*m.6">martingale:tradeAgain</field>
                                        <value name="VALUE">
                                          <block type="logic_boolean" id="v}*;H=73;[WKn2R,+.0P">
                                            <field name="BOOL">TRUE</field>
                                          </block>
                                        </value>
                                      </block>
                                    </statement>
                                    <statement name="ELSE">
                                      <block type="text_join" id="0Q-B~fTe|,QnY@(c,h@*">
                                        <field name="VARIABLE" id="5SwcMzq.f)VNUzjbKfrw">Notification:lossThresholdReached</field>
                                        <statement name="STACK">
                                          <block type="text_statement" id="db1K?]^sdr=ocll68sJz">
                                            <value name="TEXT">
                                              <shadow type="text" id="{lVc8F}w58h0szOx[bg;">
                                                <field name="TEXT">Loss threshold triggered. Total Loss:</field>
                                              </shadow>
                                            </value>
                                            <next>
                                              <block type="text_statement" id="Wf^WII2`tL|r}@bNbN[o">
                                                <value name="TEXT">
                                                  <shadow type="text" id="V1(,zn;K%.HmY,tgb1M}">
                                                    <field name="TEXT"></field>
                                                  </shadow>
                                                  <block type="math_single" id="`6,2Jm!UJarPK~GWrlBz">
                                                    <field name="OP">NEG</field>
                                                    <value name="NUM">
                                                      <shadow type="math_number" id="G8ef?0_W]w@F^R-t$p(R">
                                                        <field name="NUM">9</field>
                                                      </shadow>
                                                      <block type="variables_get" id="1(j3)T@W,~*yuT=FOi%.">
                                                        <field name="VAR" id="Kb@{Vb{+5IqV=d~y*dcr">martingale:totalProfit</field>
                                                      </block>
                                                    </value>
                                                  </block>
                                                </value>
                                              </block>
                                            </next>
                                          </block>
                                        </statement>
                                        <next>
                                          <block type="notify" id="m]|Q26uexXeXd2K]pmwI">
                                            <field name="NOTIFICATION_TYPE">error</field>
                                            <field name="NOTIFICATION_SOUND">silent</field>
                                            <value name="MESSAGE">
                                              <shadow type="text" id="cqd4ZNz3n/Q=]U9T~}Fo">
                                                <field name="TEXT">abc</field>
                                              </shadow>
                                              <block type="variables_get" id="s~}j8C,=?{Gryuj}0V6R">
                                                <field name="VAR" id="5SwcMzq.f)VNUzjbKfrw">Notification:lossThresholdReached</field>
                                              </block>
                                            </value>
                                            <next>
                                              <block type="text_print" id="7Hu/[~lR.t.}-Yj{1)Uz">
                                                <value name="TEXT">
                                                  <shadow type="text" id="^$lOuQCZ:)HXORI[Rznq">
                                                    <field name="TEXT">abc</field>
                                                  </shadow>
                                                  <block type="variables_get" id="FovJWy:zEzG5q}JWeVtB">
                                                    <field name="VAR" id="5SwcMzq.f)VNUzjbKfrw">Notification:lossThresholdReached</field>
                                                  </block>
                                                </value>
                                              </block>
                                            </next>
                                          </block>
                                        </next>
                                      </block>
                                    </statement>
                                  </block>
                                </statement>
                                <statement name="ELSE">
                                  <block type="text_join" id="[A$i5JA+{nps8EN,kgnS">
                                    <field name="VARIABLE" id="I--KAm(C+#{d?~ip*23e">Notification:profitThresholdReached</field>
                                    <statement name="STACK">
                                      <block type="text_statement" id="*d%K,c1?SW4n,rFX.*li">
                                        <value name="TEXT">
                                          <shadow type="text" id="weGes?KSjTg7EPpK}{.2">
                                            <field name="TEXT">Profit threshold triggered. Total Profit:</field>
                                          </shadow>
                                        </value>
                                        <next>
                                          <block type="text_statement" id="-:.y|:f5RYmLM+7|FWbi">
                                            <value name="TEXT">
                                              <shadow type="text" id="by,p9;WXlWxty;P|:Ckw">
                                                <field name="TEXT"></field>
                                              </shadow>
                                              <block type="variables_get" id="vkzm7ZsfkqpuUv[-mVlL">
                                                <field name="VAR" id="Kb@{Vb{+5IqV=d~y*dcr">martingale:totalProfit</field>
                                              </block>
                                            </value>
                                          </block>
                                        </next>
                                      </block>
                                    </statement>
                                    <next>
                                      <block type="notify" id="^j7RbTu|i5~9Q?vzbn)f">
                                        <field name="NOTIFICATION_TYPE">success</field>
                                        <field name="NOTIFICATION_SOUND">silent</field>
                                        <value name="MESSAGE">
                                          <shadow type="text" id="XEJ;!-fXf)0L!I1S{W(-">
                                            <field name="TEXT">abc</field>
                                          </shadow>
                                          <block type="variables_get" id="rdHLeQSw83!sVrwwf:bU">
                                            <field name="VAR" id="I--KAm(C+#{d?~ip*23e">Notification:profitThresholdReached</field>
                                          </block>
                                        </value>
                                        <next>
                                          <block type="text_print" id="(3se7`318IM+E4L`y]h*">
                                            <value name="TEXT">
                                              <shadow type="text" id="My#q$t~V(?O05c-+,i{N">
                                                <field name="TEXT">abc</field>
                                              </shadow>
                                              <block type="variables_get" id="fec1s;/PX|TlCC@)Yf{F">
                                                <field name="VAR" id="I--KAm(C+#{d?~ip*23e">Notification:profitThresholdReached</field>
                                              </block>
                                            </value>
                                          </block>
                                        </next>
                                      </block>
                                    </next>
                                  </block>
                                </statement>
                              </block>
                            </next>
                          </block>
                        </next>
                      </block>
                    </next>
                  </block>
                </next>
              </block>
            </next>
          </block>
        </next>
      </block>
    </statement>
    <value name="RETURN">
      <block type="variables_get" id="j?CldGzC$5jEF4LPS]9j">
        <field name="VAR" id="6G^6o^Ic@rjF|sHv*m.6">martingale:tradeAgain</field>
      </block>
    </value>
  </block>
</xml>
<!---
kiriungi/kiriungi is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
