                                      1 ;--------------------------------------------------------
                                      2 ; File Created by SDCC : free open source ANSI-C Compiler
                                      3 ; Version 3.5.0 #9253 (Jun 20 2015) (MINGW64)
                                      4 ; This file was generated Sat Jun 04 12:50:09 2016
                                      5 ;--------------------------------------------------------
                                      6 	.module timers
                                      7 	.optsdcc -mmcs51 --model-small
                                      8 	
                                      9 ;--------------------------------------------------------
                                     10 ; Public variables in this module
                                     11 ;--------------------------------------------------------
                                     12 	.globl _tmr0isr
                                     13 	.globl _tmr1isr
                                     14 	.globl _RI
                                     15 	.globl _TI
                                     16 	.globl _RB8
                                     17 	.globl _TB8
                                     18 	.globl _REN
                                     19 	.globl _SM2
                                     20 	.globl _SM1
                                     21 	.globl _SM0
                                     22 	.globl _RXD
                                     23 	.globl _TXD
                                     24 	.globl _INT0
                                     25 	.globl _INT1
                                     26 	.globl _T0
                                     27 	.globl _T1
                                     28 	.globl _WR
                                     29 	.globl _RD
                                     30 	.globl _PX0
                                     31 	.globl _PT0
                                     32 	.globl _PX1
                                     33 	.globl _PT1
                                     34 	.globl _PS
                                     35 	.globl _EX0
                                     36 	.globl _ET0
                                     37 	.globl _EX1
                                     38 	.globl _ET1
                                     39 	.globl _ES
                                     40 	.globl _EA
                                     41 	.globl _IT0
                                     42 	.globl _IE0
                                     43 	.globl _IT1
                                     44 	.globl _IE1
                                     45 	.globl _TR0
                                     46 	.globl _TF0
                                     47 	.globl _TR1
                                     48 	.globl _TF1
                                     49 	.globl _P
                                     50 	.globl _OV
                                     51 	.globl _RS0
                                     52 	.globl _RS1
                                     53 	.globl _F0
                                     54 	.globl _AC
                                     55 	.globl _CY
                                     56 	.globl _SBUF
                                     57 	.globl _SCON
                                     58 	.globl _IP
                                     59 	.globl _IE
                                     60 	.globl _TH1
                                     61 	.globl _TH0
                                     62 	.globl _TL1
                                     63 	.globl _TL0
                                     64 	.globl _TMOD
                                     65 	.globl _TCON
                                     66 	.globl _PCON
                                     67 	.globl _DPH
                                     68 	.globl _DPL
                                     69 	.globl _SP
                                     70 	.globl _B
                                     71 	.globl _ACC
                                     72 	.globl _PSW
                                     73 	.globl _P3
                                     74 	.globl _P2
                                     75 	.globl _P1
                                     76 	.globl _P0
                                     77 	.globl _PRAMCTL
                                     78 	.globl _BANK2PAH
                                     79 	.globl _BANK2PAL
                                     80 	.globl _BANK2VA
                                     81 	.globl _BANK1PAH
                                     82 	.globl _BANK1PAL
                                     83 	.globl _BANK1VA
                                     84 	.globl _BANK0PAH
                                     85 	.globl _BANK0PAL
                                     86 	.globl _WARMSTATUS
                                     87 	.globl _GPIO0OUT
                                     88 	.globl _GPIO0DIR
                                     89 	.globl _DMACMD
                                     90 	.globl _DMAFILL3
                                     91 	.globl _DMAFILL2
                                     92 	.globl _DMAFILL1
                                     93 	.globl _DMAFILL0
                                     94 	.globl _DMASIZEH
                                     95 	.globl _DMASIZEM
                                     96 	.globl _DMASIZEL
                                     97 	.globl _DMADSTH
                                     98 	.globl _DMADSTM
                                     99 	.globl _DMADSTL
                                    100 	.globl _DMASRCH
                                    101 	.globl _DMASRCM
                                    102 	.globl _DMASRCL
                                    103 	.globl _NANDCSDIR
                                    104 	.globl _NANDCSOUT
                                    105 	.globl _EP4
                                    106 	.globl _EP3
                                    107 	.globl _EP2
                                    108 	.globl _EP1
                                    109 	.globl _EP0
                                    110 	.globl _SETUPDAT
                                    111 	.globl _EP0CS
                                    112 	.globl _EPIE
                                    113 	.globl _EPIRQ
                                    114 	.globl _USBIRQ
                                    115 	.globl _USBSTAT
                                    116 	.globl _USBCTL
                                    117 	.globl _REGBANK
                                    118 	.globl _InitTicks
                                    119 	.globl _GetTickCount
                                    120 	.globl _SetLEDThreshold
                                    121 	.globl _InitLED
                                    122 	.globl _LEDBlink
                                    123 	.globl _LEDOff
                                    124 ;--------------------------------------------------------
                                    125 ; special function registers
                                    126 ;--------------------------------------------------------
                                    127 	.area RSEG    (ABS,DATA)
      000000                        128 	.org 0x0000
                           000080   129 _P0	=	0x0080
                           000090   130 _P1	=	0x0090
                           0000A0   131 _P2	=	0x00a0
                           0000B0   132 _P3	=	0x00b0
                           0000D0   133 _PSW	=	0x00d0
                           0000E0   134 _ACC	=	0x00e0
                           0000F0   135 _B	=	0x00f0
                           000081   136 _SP	=	0x0081
                           000082   137 _DPL	=	0x0082
                           000083   138 _DPH	=	0x0083
                           000087   139 _PCON	=	0x0087
                           000088   140 _TCON	=	0x0088
                           000089   141 _TMOD	=	0x0089
                           00008A   142 _TL0	=	0x008a
                           00008B   143 _TL1	=	0x008b
                           00008C   144 _TH0	=	0x008c
                           00008D   145 _TH1	=	0x008d
                           0000A8   146 _IE	=	0x00a8
                           0000B8   147 _IP	=	0x00b8
                           000098   148 _SCON	=	0x0098
                           000099   149 _SBUF	=	0x0099
                                    150 ;--------------------------------------------------------
                                    151 ; special function bits
                                    152 ;--------------------------------------------------------
                                    153 	.area RSEG    (ABS,DATA)
      000000                        154 	.org 0x0000
                           0000D7   155 _CY	=	0x00d7
                           0000D6   156 _AC	=	0x00d6
                           0000D5   157 _F0	=	0x00d5
                           0000D4   158 _RS1	=	0x00d4
                           0000D3   159 _RS0	=	0x00d3
                           0000D2   160 _OV	=	0x00d2
                           0000D0   161 _P	=	0x00d0
                           00008F   162 _TF1	=	0x008f
                           00008E   163 _TR1	=	0x008e
                           00008D   164 _TF0	=	0x008d
                           00008C   165 _TR0	=	0x008c
                           00008B   166 _IE1	=	0x008b
                           00008A   167 _IT1	=	0x008a
                           000089   168 _IE0	=	0x0089
                           000088   169 _IT0	=	0x0088
                           0000AF   170 _EA	=	0x00af
                           0000AC   171 _ES	=	0x00ac
                           0000AB   172 _ET1	=	0x00ab
                           0000AA   173 _EX1	=	0x00aa
                           0000A9   174 _ET0	=	0x00a9
                           0000A8   175 _EX0	=	0x00a8
                           0000BC   176 _PS	=	0x00bc
                           0000BB   177 _PT1	=	0x00bb
                           0000BA   178 _PX1	=	0x00ba
                           0000B9   179 _PT0	=	0x00b9
                           0000B8   180 _PX0	=	0x00b8
                           0000B7   181 _RD	=	0x00b7
                           0000B6   182 _WR	=	0x00b6
                           0000B5   183 _T1	=	0x00b5
                           0000B4   184 _T0	=	0x00b4
                           0000B3   185 _INT1	=	0x00b3
                           0000B2   186 _INT0	=	0x00b2
                           0000B1   187 _TXD	=	0x00b1
                           0000B0   188 _RXD	=	0x00b0
                           00009F   189 _SM0	=	0x009f
                           00009E   190 _SM1	=	0x009e
                           00009D   191 _SM2	=	0x009d
                           00009C   192 _REN	=	0x009c
                           00009B   193 _TB8	=	0x009b
                           00009A   194 _RB8	=	0x009a
                           000099   195 _TI	=	0x0099
                           000098   196 _RI	=	0x0098
                                    197 ;--------------------------------------------------------
                                    198 ; overlayable register banks
                                    199 ;--------------------------------------------------------
                                    200 	.area REG_BANK_0	(REL,OVR,DATA)
      000000                        201 	.ds 8
                                    202 ;--------------------------------------------------------
                                    203 ; internal ram data
                                    204 ;--------------------------------------------------------
                                    205 	.area DSEG    (DATA)
      000013                        206 _tmr0count:
      000013                        207 	.ds 1
      000014                        208 _led_ticks:
      000014                        209 	.ds 1
      000015                        210 _led_timer:
      000015                        211 	.ds 1
      000016                        212 _led_tick_threshold:
      000016                        213 	.ds 1
      000017                        214 _tmr1count:
      000017                        215 	.ds 1
      000018                        216 _tmr1reload:
      000018                        217 	.ds 2
                                    218 ;--------------------------------------------------------
                                    219 ; overlayable items in internal ram 
                                    220 ;--------------------------------------------------------
                                    221 	.area	OSEG    (OVR,DATA)
                                    222 ;--------------------------------------------------------
                                    223 ; indirectly addressable internal ram data
                                    224 ;--------------------------------------------------------
                                    225 	.area ISEG    (DATA)
                                    226 ;--------------------------------------------------------
                                    227 ; absolute internal ram data
                                    228 ;--------------------------------------------------------
                                    229 	.area IABS    (ABS,DATA)
                                    230 	.area IABS    (ABS,DATA)
                                    231 ;--------------------------------------------------------
                                    232 ; bit data
                                    233 ;--------------------------------------------------------
                                    234 	.area BSEG    (BIT)
                                    235 ;--------------------------------------------------------
                                    236 ; paged external ram data
                                    237 ;--------------------------------------------------------
                                    238 	.area PSEG    (PAG,XDATA)
                                    239 ;--------------------------------------------------------
                                    240 ; external ram data
                                    241 ;--------------------------------------------------------
                                    242 	.area XSEG    (XDATA)
                           00F000   243 _REGBANK	=	0xf000
                           00F008   244 _USBCTL	=	0xf008
                           00F009   245 _USBSTAT	=	0xf009
                           00F027   246 _USBIRQ	=	0xf027
                           00F020   247 _EPIRQ	=	0xf020
                           00F030   248 _EPIE	=	0xf030
                           00F048   249 _EP0CS	=	0xf048
                           00F0B8   250 _SETUPDAT	=	0xf0b8
                           00F1C0   251 _EP0	=	0xf1c0
                           00F200   252 _EP1	=	0xf200
                           00F240   253 _EP2	=	0xf240
                           00F280   254 _EP3	=	0xf280
                           00F2C0   255 _EP4	=	0xf2c0
                           00F608   256 _NANDCSOUT	=	0xf608
                           00F618   257 _NANDCSDIR	=	0xf618
                           00F900   258 _DMASRCL	=	0xf900
                           00F901   259 _DMASRCM	=	0xf901
                           00F902   260 _DMASRCH	=	0xf902
                           00F904   261 _DMADSTL	=	0xf904
                           00F905   262 _DMADSTM	=	0xf905
                           00F906   263 _DMADSTH	=	0xf906
                           00F908   264 _DMASIZEL	=	0xf908
                           00F909   265 _DMASIZEM	=	0xf909
                           00F90A   266 _DMASIZEH	=	0xf90a
                           00F90C   267 _DMAFILL0	=	0xf90c
                           00F90D   268 _DMAFILL1	=	0xf90d
                           00F90E   269 _DMAFILL2	=	0xf90e
                           00F90F   270 _DMAFILL3	=	0xf90f
                           00F930   271 _DMACMD	=	0xf930
                           00FA14   272 _GPIO0DIR	=	0xfa14
                           00FA15   273 _GPIO0OUT	=	0xfa15
                           00FA38   274 _WARMSTATUS	=	0xfa38
                           00FA40   275 _BANK0PAL	=	0xfa40
                           00FA41   276 _BANK0PAH	=	0xfa41
                           00FA42   277 _BANK1VA	=	0xfa42
                           00FA43   278 _BANK1PAL	=	0xfa43
                           00FA44   279 _BANK1PAH	=	0xfa44
                           00FA45   280 _BANK2VA	=	0xfa45
                           00FA46   281 _BANK2PAL	=	0xfa46
                           00FA47   282 _BANK2PAH	=	0xfa47
                           00FA48   283 _PRAMCTL	=	0xfa48
                                    284 ;--------------------------------------------------------
                                    285 ; absolute external ram data
                                    286 ;--------------------------------------------------------
                                    287 	.area XABS    (ABS,XDATA)
                                    288 ;--------------------------------------------------------
                                    289 ; external initialized ram data
                                    290 ;--------------------------------------------------------
                                    291 	.area XISEG   (XDATA)
                                    292 	.area HOME    (CODE)
                                    293 	.area GSINIT0 (CODE)
                                    294 	.area GSINIT1 (CODE)
                                    295 	.area GSINIT2 (CODE)
                                    296 	.area GSINIT3 (CODE)
                                    297 	.area GSINIT4 (CODE)
                                    298 	.area GSINIT5 (CODE)
                                    299 	.area GSINIT  (CODE)
                                    300 	.area GSFINAL (CODE)
                                    301 	.area CSEG    (CODE)
                                    302 ;--------------------------------------------------------
                                    303 ; global & static initialisations
                                    304 ;--------------------------------------------------------
                                    305 	.area HOME    (CODE)
                                    306 	.area GSINIT  (CODE)
                                    307 	.area GSFINAL (CODE)
                                    308 	.area GSINIT  (CODE)
                                    309 ;--------------------------------------------------------
                                    310 ; Home
                                    311 ;--------------------------------------------------------
                                    312 	.area HOME    (CODE)
                                    313 	.area HOME    (CODE)
                                    314 ;--------------------------------------------------------
                                    315 ; code
                                    316 ;--------------------------------------------------------
                                    317 	.area CSEG    (CODE)
                                    318 ;------------------------------------------------------------
                                    319 ;Allocation info for local variables in function 'tmr1isr'
                                    320 ;------------------------------------------------------------
                                    321 ;	timers.c:8: void tmr1isr(void) __interrupt TMR1_VECT
                                    322 ;	-----------------------------------------
                                    323 ;	 function tmr1isr
                                    324 ;	-----------------------------------------
      0002FD                        325 _tmr1isr:
                           000007   326 	ar7 = 0x07
                           000006   327 	ar6 = 0x06
                           000005   328 	ar5 = 0x05
                           000004   329 	ar4 = 0x04
                           000003   330 	ar3 = 0x03
                           000002   331 	ar2 = 0x02
                           000001   332 	ar1 = 0x01
                           000000   333 	ar0 = 0x00
      0002FD C0 07            [24]  334 	push	ar7
      0002FF C0 06            [24]  335 	push	ar6
      000301 C0 D0            [24]  336 	push	psw
      000303 75 D0 00         [24]  337 	mov	psw,#0x00
                                    338 ;	timers.c:10: TR1 = 0;
      000306 C2 8E            [12]  339 	clr	_TR1
                                    340 ;	timers.c:11: TH1 = MSB(tmr1reload);
      000308 AF 19            [24]  341 	mov	r7,(_tmr1reload + 1)
      00030A 8F 8D            [24]  342 	mov	_TH1,r7
                                    343 ;	timers.c:12: TL1 = LSB(tmr1reload);
      00030C AE 18            [24]  344 	mov	r6,_tmr1reload
      00030E 8E 8B            [24]  345 	mov	_TL1,r6
                                    346 ;	timers.c:13: tmr1count++;
      000310 05 17            [12]  347 	inc	_tmr1count
                                    348 ;	timers.c:14: TR1 = 1;
      000312 D2 8E            [12]  349 	setb	_TR1
      000314 D0 D0            [24]  350 	pop	psw
      000316 D0 06            [24]  351 	pop	ar6
      000318 D0 07            [24]  352 	pop	ar7
      00031A 32               [24]  353 	reti
                                    354 ;	eliminated unneeded push/pop dpl
                                    355 ;	eliminated unneeded push/pop dph
                                    356 ;	eliminated unneeded push/pop b
                                    357 ;	eliminated unneeded push/pop acc
                                    358 ;------------------------------------------------------------
                                    359 ;Allocation info for local variables in function 'InitTicks'
                                    360 ;------------------------------------------------------------
                                    361 ;	timers.c:17: void InitTicks()
                                    362 ;	-----------------------------------------
                                    363 ;	 function InitTicks
                                    364 ;	-----------------------------------------
      00031B                        365 _InitTicks:
                                    366 ;	timers.c:19: if (XVAL(0xFA60) == 0x0F)
      00031B 90 FA 60         [24]  367 	mov	dptr,#0xFA60
      00031E E0               [24]  368 	movx	a,@dptr
      00031F FF               [12]  369 	mov	r7,a
      000320 BF 0F 08         [24]  370 	cjne	r7,#0x0F,00102$
                                    371 ;	timers.c:21: tmr1reload = 0xF63C;
      000323 75 18 3C         [24]  372 	mov	_tmr1reload,#0x3C
      000326 75 19 F6         [24]  373 	mov	(_tmr1reload + 1),#0xF6
      000329 80 23            [24]  374 	sjmp	00103$
      00032B                        375 00102$:
                                    376 ;	timers.c:25: tmr1reload = 0-(2500/(XVAL(0xFA60)+2));
      00032B 90 FA 60         [24]  377 	mov	dptr,#0xFA60
      00032E E0               [24]  378 	movx	a,@dptr
      00032F FF               [12]  379 	mov	r7,a
      000330 7E 00            [12]  380 	mov	r6,#0x00
      000332 74 02            [12]  381 	mov	a,#0x02
      000334 2F               [12]  382 	add	a,r7
      000335 F5 45            [12]  383 	mov	__divsint_PARM_2,a
      000337 E4               [12]  384 	clr	a
      000338 3E               [12]  385 	addc	a,r6
      000339 F5 46            [12]  386 	mov	(__divsint_PARM_2 + 1),a
      00033B 90 09 C4         [24]  387 	mov	dptr,#0x09C4
      00033E 12 0F F0         [24]  388 	lcall	__divsint
      000341 AE 82            [24]  389 	mov	r6,dpl
      000343 AF 83            [24]  390 	mov	r7,dph
      000345 C3               [12]  391 	clr	c
      000346 E4               [12]  392 	clr	a
      000347 9E               [12]  393 	subb	a,r6
      000348 F5 18            [12]  394 	mov	_tmr1reload,a
      00034A E4               [12]  395 	clr	a
      00034B 9F               [12]  396 	subb	a,r7
      00034C F5 19            [12]  397 	mov	(_tmr1reload + 1),a
      00034E                        398 00103$:
                                    399 ;	timers.c:28: tmr1count = 0;
      00034E 75 17 00         [24]  400 	mov	_tmr1count,#0x00
                                    401 ;	timers.c:29: TR1 = 0;
      000351 C2 8E            [12]  402 	clr	_TR1
                                    403 ;	timers.c:30: ET1 = 1;
      000353 D2 AB            [12]  404 	setb	_ET1
                                    405 ;	timers.c:31: TMOD = TMOD & 0x0F | 0x10;
      000355 74 0F            [12]  406 	mov	a,#0x0F
      000357 55 89            [12]  407 	anl	a,_TMOD
      000359 44 10            [12]  408 	orl	a,#0x10
      00035B F5 89            [12]  409 	mov	_TMOD,a
      00035D 22               [24]  410 	ret
                                    411 ;------------------------------------------------------------
                                    412 ;Allocation info for local variables in function 'GetTickCount'
                                    413 ;------------------------------------------------------------
                                    414 ;	timers.c:34: BYTE GetTickCount(void)
                                    415 ;	-----------------------------------------
                                    416 ;	 function GetTickCount
                                    417 ;	-----------------------------------------
      00035E                        418 _GetTickCount:
                                    419 ;	timers.c:36: return tmr1count;
      00035E 85 17 82         [24]  420 	mov	dpl,_tmr1count
      000361 22               [24]  421 	ret
                                    422 ;------------------------------------------------------------
                                    423 ;Allocation info for local variables in function 'tmr0isr'
                                    424 ;------------------------------------------------------------
                                    425 ;	timers.c:39: void tmr0isr(void) __interrupt TMR0_VECT
                                    426 ;	-----------------------------------------
                                    427 ;	 function tmr0isr
                                    428 ;	-----------------------------------------
      000362                        429 _tmr0isr:
      000362 C0 E0            [24]  430 	push	acc
      000364 C0 82            [24]  431 	push	dpl
      000366 C0 83            [24]  432 	push	dph
      000368 C0 07            [24]  433 	push	ar7
      00036A C0 D0            [24]  434 	push	psw
      00036C 75 D0 00         [24]  435 	mov	psw,#0x00
                                    436 ;	timers.c:42: TR0 = 0;
      00036F C2 8C            [12]  437 	clr	_TR0
                                    438 ;	timers.c:43: TL0 = 0xE6;
      000371 75 8A E6         [24]  439 	mov	_TL0,#0xE6
                                    440 ;	timers.c:44: TH0 = 0x96;
      000374 75 8C 96         [24]  441 	mov	_TH0,#0x96
                                    442 ;	timers.c:45: TR0 = 1;
      000377 D2 8C            [12]  443 	setb	_TR0
                                    444 ;	timers.c:47: if ((GPIO0OUT & 2) == 0) //turned off
      000379 90 FA 15         [24]  445 	mov	dptr,#_GPIO0OUT
      00037C E0               [24]  446 	movx	a,@dptr
      00037D FF               [12]  447 	mov	r7,a
      00037E 20 E1 02         [24]  448 	jb	acc.1,00102$
                                    449 ;	timers.c:49: return;
      000381 80 54            [24]  450 	sjmp	00114$
      000383                        451 00102$:
                                    452 ;	timers.c:52: tmr0count++;
      000383 05 13            [12]  453 	inc	_tmr0count
                                    454 ;	timers.c:53: led_ticks++;
      000385 05 14            [12]  455 	inc	_led_ticks
                                    456 ;	timers.c:54: if (led_ticks < led_tick_threshold)
      000387 C3               [12]  457 	clr	c
      000388 E5 14            [12]  458 	mov	a,_led_ticks
      00038A 95 16            [12]  459 	subb	a,_led_tick_threshold
      00038C 50 02            [24]  460 	jnc	00104$
                                    461 ;	timers.c:56: return;
      00038E 80 47            [24]  462 	sjmp	00114$
      000390                        463 00104$:
                                    464 ;	timers.c:59: led_ticks = 0;
      000390 75 14 00         [24]  465 	mov	_led_ticks,#0x00
                                    466 ;	timers.c:60: if (led_timer >= 31)
      000393 74 E1            [12]  467 	mov	a,#0x100 - 0x1F
      000395 25 15            [12]  468 	add	a,_led_timer
      000397 50 0B            [24]  469 	jnc	00106$
                                    470 ;	timers.c:62: GPIO0OUT = 1;
      000399 90 FA 15         [24]  471 	mov	dptr,#_GPIO0OUT
      00039C 74 01            [12]  472 	mov	a,#0x01
      00039E F0               [24]  473 	movx	@dptr,a
                                    474 ;	timers.c:63: led_timer = 0;		
      00039F 75 15 00         [24]  475 	mov	_led_timer,#0x00
                                    476 ;	timers.c:64: return;
      0003A2 80 33            [24]  477 	sjmp	00114$
      0003A4                        478 00106$:
                                    479 ;	timers.c:67: if (led_timer >= 10)
      0003A4 74 F6            [12]  480 	mov	a,#0x100 - 0x0A
      0003A6 25 15            [12]  481 	add	a,_led_timer
      0003A8 50 0B            [24]  482 	jnc	00108$
                                    483 ;	timers.c:69: GPIO0OUT = ~GPIO0OUT;
      0003AA 90 FA 15         [24]  484 	mov	dptr,#_GPIO0OUT
      0003AD E0               [24]  485 	movx	a,@dptr
      0003AE FF               [12]  486 	mov	r7,a
      0003AF F4               [12]  487 	cpl	a
      0003B0 F0               [24]  488 	movx	@dptr,a
                                    489 ;	timers.c:70: led_timer++;
      0003B1 05 15            [12]  490 	inc	_led_timer
                                    491 ;	timers.c:71: return;
      0003B3 80 22            [24]  492 	sjmp	00114$
      0003B5                        493 00108$:
                                    494 ;	timers.c:74: if (led_timer == 0)
      0003B5 E5 15            [12]  495 	mov	a,_led_timer
      0003B7 70 02            [24]  496 	jnz	00110$
                                    497 ;	timers.c:76: return;
      0003B9 80 1C            [24]  498 	sjmp	00114$
      0003BB                        499 00110$:
                                    500 ;	timers.c:79: if (GPIO0OUT & 1)
      0003BB 90 FA 15         [24]  501 	mov	dptr,#_GPIO0OUT
      0003BE E0               [24]  502 	movx	a,@dptr
      0003BF FF               [12]  503 	mov	r7,a
      0003C0 30 E0 0B         [24]  504 	jnb	acc.0,00112$
                                    505 ;	timers.c:81: GPIO0OUT &= 0xFE;
      0003C3 90 FA 15         [24]  506 	mov	dptr,#_GPIO0OUT
      0003C6 E0               [24]  507 	movx	a,@dptr
      0003C7 FF               [12]  508 	mov	r7,a
      0003C8 74 FE            [12]  509 	mov	a,#0xFE
      0003CA 5F               [12]  510 	anl	a,r7
      0003CB F0               [24]  511 	movx	@dptr,a
      0003CC 80 09            [24]  512 	sjmp	00114$
      0003CE                        513 00112$:
                                    514 ;	timers.c:85: GPIO0OUT |= 1;
      0003CE 90 FA 15         [24]  515 	mov	dptr,#_GPIO0OUT
      0003D1 E0               [24]  516 	movx	a,@dptr
      0003D2 FF               [12]  517 	mov	r7,a
      0003D3 74 01            [12]  518 	mov	a,#0x01
      0003D5 4F               [12]  519 	orl	a,r7
      0003D6 F0               [24]  520 	movx	@dptr,a
      0003D7                        521 00114$:
      0003D7 D0 D0            [24]  522 	pop	psw
      0003D9 D0 07            [24]  523 	pop	ar7
      0003DB D0 83            [24]  524 	pop	dph
      0003DD D0 82            [24]  525 	pop	dpl
      0003DF D0 E0            [24]  526 	pop	acc
      0003E1 32               [24]  527 	reti
                                    528 ;	eliminated unneeded push/pop b
                                    529 ;------------------------------------------------------------
                                    530 ;Allocation info for local variables in function 'SetLEDThreshold'
                                    531 ;------------------------------------------------------------
                                    532 ;threshold                 Allocated to registers r6 r7 
                                    533 ;------------------------------------------------------------
                                    534 ;	timers.c:89: void SetLEDThreshold(int threshold)
                                    535 ;	-----------------------------------------
                                    536 ;	 function SetLEDThreshold
                                    537 ;	-----------------------------------------
      0003E2                        538 _SetLEDThreshold:
      0003E2 AE 82            [24]  539 	mov	r6,dpl
                                    540 ;	timers.c:91: led_tick_threshold = threshold;
      0003E4 8E 16            [24]  541 	mov	_led_tick_threshold,r6
      0003E6 22               [24]  542 	ret
                                    543 ;------------------------------------------------------------
                                    544 ;Allocation info for local variables in function 'InitLED'
                                    545 ;------------------------------------------------------------
                                    546 ;	timers.c:94: void InitLED(void)
                                    547 ;	-----------------------------------------
                                    548 ;	 function InitLED
                                    549 ;	-----------------------------------------
      0003E7                        550 _InitLED:
                                    551 ;	timers.c:96: led_tick_threshold = 100;
      0003E7 75 16 64         [24]  552 	mov	_led_tick_threshold,#0x64
                                    553 ;	timers.c:97: tmr0count = 0;
      0003EA 75 13 00         [24]  554 	mov	_tmr0count,#0x00
                                    555 ;	timers.c:98: GPIO0OUT = 3;
      0003ED 90 FA 15         [24]  556 	mov	dptr,#_GPIO0OUT
      0003F0 74 03            [12]  557 	mov	a,#0x03
      0003F2 F0               [24]  558 	movx	@dptr,a
                                    559 ;	timers.c:99: led_ticks = 0;
      0003F3 75 14 00         [24]  560 	mov	_led_ticks,#0x00
                                    561 ;	timers.c:100: led_timer = 0;
      0003F6 75 15 00         [24]  562 	mov	_led_timer,#0x00
                                    563 ;	timers.c:101: EA = 1;
      0003F9 D2 AF            [12]  564 	setb	_EA
                                    565 ;	timers.c:102: ET0 = 1;
      0003FB D2 A9            [12]  566 	setb	_ET0
                                    567 ;	timers.c:103: TR0 = 1;
      0003FD D2 8C            [12]  568 	setb	_TR0
      0003FF 22               [24]  569 	ret
                                    570 ;------------------------------------------------------------
                                    571 ;Allocation info for local variables in function 'LEDBlink'
                                    572 ;------------------------------------------------------------
                                    573 ;	timers.c:106: void LEDBlink(void)
                                    574 ;	-----------------------------------------
                                    575 ;	 function LEDBlink
                                    576 ;	-----------------------------------------
      000400                        577 _LEDBlink:
                                    578 ;	timers.c:108: GPIO0OUT = 2;
      000400 90 FA 15         [24]  579 	mov	dptr,#_GPIO0OUT
      000403 74 02            [12]  580 	mov	a,#0x02
      000405 F0               [24]  581 	movx	@dptr,a
                                    582 ;	timers.c:109: led_timer = 1;
      000406 75 15 01         [24]  583 	mov	_led_timer,#0x01
      000409 22               [24]  584 	ret
                                    585 ;------------------------------------------------------------
                                    586 ;Allocation info for local variables in function 'LEDOff'
                                    587 ;------------------------------------------------------------
                                    588 ;	timers.c:112: void LEDOff(void)
                                    589 ;	-----------------------------------------
                                    590 ;	 function LEDOff
                                    591 ;	-----------------------------------------
      00040A                        592 _LEDOff:
                                    593 ;	timers.c:114: GPIO0OUT = 3;
      00040A 90 FA 15         [24]  594 	mov	dptr,#_GPIO0OUT
      00040D 74 03            [12]  595 	mov	a,#0x03
      00040F F0               [24]  596 	movx	@dptr,a
                                    597 ;	timers.c:115: led_timer = 0;
      000410 75 15 00         [24]  598 	mov	_led_timer,#0x00
      000413 22               [24]  599 	ret
                                    600 	.area CSEG    (CODE)
                                    601 	.area CONST   (CODE)
                                    602 	.area XINIT   (CODE)
                                    603 	.area CABS    (ABS,CODE)
