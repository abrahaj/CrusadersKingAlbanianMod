Arberia Mod for CKII
==============================
This mod adds the possibility to play as Albanian (Arberia) in the Crusader's King II game. For some reason the CKII has completely wiped traces of Arberesh in the game. Some great Albanian families are mixed for Serbian or Greek (See below correction on dynasties). 
 
-----
## Mod Information
* [GitHub Source](https://github.com/abrahaj/CrusadersKingAlbanianMod)
* [Albforumi - Forum Discussions](http://forumi.shqiperia.com/threads/paradox-crusaders-king-play-as-albanian-arberia.30247/)


## How to use the Mod

[Download the files](https://github.com/abrahaj/CrusadersKingAlbanianMod/archive/master.zip) and place them under *C:\Users\{YOURUSER}\Documents\Paradox Interactive\Crusader Kings II\mod* in your Windows Version. The same should be done with the Linux version, but the path to the mods dir will change slightly. 


Start the game and if everything worked fine, you should see the "Arberia" Mod in the mods section ![Printscreen ](http://i.imgur.com/4Vb4AfU.png)

At the moment the mod relies on the [The Ruler Designer](http://www.ckiiwiki.com/Ruler_Designer) DLC is needed to start the game as an Albanian. I did not investigate much time to change the initial Dynasties, but in theory should be possible to start the game as Albanian without this DLC as well. 

Go to Dyrrachion, and change the leader with the Ruler Design. In the attributes section pick ethnicity Albanian (under Latin) and change the name and dynasty as you please.

You do not need this section to play the MOD! This is an informative section in case you want to create the MOD yourself.
-----
## What was changed (or a walkthrough the changes)
In order to create such a new mod, only a few files are needed to be changed. The instructions on this section should make it easier to create such a mod in the future for other versions of Crusader's Kings.

### Add Albanian Culture
Cultures are defined under the _\common\cultures\00_cultures.txt_ file.
Under the section Latin I added the following: 

    albanian = {
  		graphical_culture = frankishgfx
  		color = { 0.7 0.7 0.1 }
  		
  		male_names = {
  			Adamat Adan Adomat Adriatik Afrim Agim Agimor Agrin Agron Aidan Aigin Aimir Akal Alaron Alasin Alban Albanor Album Algas Alk Alkan Almarin Alper Altin Alzan Alzen Alzet Amant
  			Amantin Amat Aranit Arben Arbenor Arber Arberesh Arberor Arbi Arbian Arbor Ardit Ardian Argjel Argjend Argjendor Arianit Aril Arion Arlind Armir Artar Artas Artian Asdrea 
  			Astrit Adrian Arber Armant Bardh Bardyl Bato Bekim Bindi Bud Bushat Komin Dardan Dede Dimiter Doda Dukagjin Engjell Faton Gent Gjergj Gjin Gjon Gjon-Leke Gjonja Grgur Gulam 
  			Guxim Hekuran Ilija Karl Koll Marin Nikoll Kosta Konstandin Kristofor Kujtim Lale Leke Llesh Lul Lulezim Lum Marin Marka Martin Mehill Mentuli Mik Miri Moisi Muriq Muzak
  			Naum Nderim Ndue Ndre Pal Paulin Pavle Pirro Pjet Prenk Progon Reposh Shqiptar Shtjefen Simon Strazimir Tanush Teodor Timomir Uke Uran Vango Viktor Vlash Xhan Zeshkan
  		}
  		female_names = {
  			Aferdita Angjelina Derra Diana Donika Drita Fane Fanushe Fluter Hana Komita Lule Majmire Mamice Mara Marena Maria Meri Mrika Pranvera Prenne Rugina Shqipe Teodora Teuta 
  			Vlajka Vojsava Yela Zana Zoje Bajame Bajuke Ballargjenda Baluke Bardha Bardhyle Baresha Bata Batona Begatia Begatime Begatore Belina Besa Besara Besarta Besforta Besiana 
  			Besime Besmira Besnike Betare Betime Bjeshka Bjeshkana Bleroshe Blerta Bora Borake Bujare Bujaresha
  		}
  		
  		from_dynasty_prefix = "prej "
  
  		modifier = default_culture_modifier
  		# Chance of male children being named after their paternal or maternal grandfather, or their father. Sum must not exceed 100.
  		pat_grf_name_chance = 30
  		mat_grf_name_chance = 10
  		father_name_chance = 25
  		
  		# Chance of female children being named after their paternal or maternal grandmother, or their mother. Sum must not exceed 100.
  		pat_grm_name_chance = 20
  		mat_grm_name_chance = 40
  		mother_name_chance = 5
  	}
The names on the list are exhaustive, please feel free to pull request with more names on the list.

## Add Localisation information for Albanian
Since we added the Albanian Culture, this should be recognized by the Localisation engine internally.
In this case a file was added under _\localisation\_ named _00_illyrikum.csv_
The filename can be anything (but it is a csv), it is important that it is under the localisation folder and the engine will retrieve it automatically
Since we had an identity crisis in middle ages, we will name the Kingdom Illyria (key is k_illyrikum and will see it in the next session) and the Culture is Albanian

    #CODE;ENGLISH;FRENCH;GERMAN;;SPANISH;;;;;;;;;x
    k_illirikum;Illyria;Illyrikum;Illyrikum;Illyrikum;;;;;;;;;x;
    albanian;Albanian;;;;;;;;;;;;;

## Creating the Kingdom
I decided to name the Kingdom Illyria! You can comply with my decision or change it as you please. To create a De Jure Kingdom, one has to modify the organization of landed_tiles under _/common/landed\_titles/landed\_titles.txt_

Under this file, find the section which starts with *e_byzantium = {* (for Byzantine Empire) and create inside this section the following kingdom:

    k_illirikum = {
    		color={ 247 77 54 }
    		color2={ 136 157 23 }
    		culture = albanian
    
    		d_dyrrachion = {
    			color={ 137 27 99 }
    			color2={ 255 255 20 }
    			
    			capital = 470 # Dyrrachion
    			
    			c_strymon = {
    				color={ 139 29 101 }
    				color2={ 255 255 20 }
    				
    				b_skopje = {
    				}
    				b_strumica = {
    				}
    				b_veles = {
    				}
    				b_prilep = {
    				}
    				b_prosek = {
    				}
    				b_trikves = {
    				}
    				b_kocane = {
    				}
    				b_kratovo = {
    				}
    			}
    			c_ochrid = {
    				color={ 141 31 103 }
    				color2={ 255 255 20 }
    				
    				greek = "Lychnidos"
    				
    				b_debar = {
    				}
    				b_ohrid = {
    					greek = "Lychnidos"
    				}
    				b_kastoria = {
    				}
    				b_kicevo = {
    				}
    				b_svetigrad = {
    				}
    				b_bitola = {
    				}
    				b_tomot = {
    				}
    				b_krusevo = {
    				}
    			}
    			c_dyrrachion = {
    				color={ 143 33 105 }
    				color2={ 255 255 20 }
    				
    				italian = "Durazzo"
    				
    				b_durazzo = {
    					greek = "Dyrrhachion"
    					italian = "Durazzo"
    				}
    				b_chounavia = {
    				}
    				b_valona = {
    				}
    				b_kruje = {
    					greek = Krougia
    				}
    				b_elbasan = {
    				}
    				b_geziq = {
    				}
    				b_spinarizza = {
    				}
    				b_beat = {
    				}
    			}
    		}
    		d_epirus = {
    			color={ 134 63 109 }
    			color2={ 255 255 20 }
    			
    			capital = 473 # Arta
    			
    			c_epeiros = {
    				color={ 138 67 113 }
    				color2={ 255 255 20 }
    				
    				b_butrint = {
    					greek = "Bouthroton"
    				}
    				b_paramythia = {
    				}
    				b_ioannina = {
    				}
    				b_sopot = {
    					greek = "Koritsa"
    				}
    				b_pogonia = {
    				}
    				b_gjirokaster = {
    					greek = Argyrokastron
    				}
    				b_igoumenitsa = {
    				}
    				b_sagiada = {
    				}
    			}
    			c_arta = {
    				color={ 142 71 117 }
    				color2={ 255 255 20 }
    				
    				b_preveza = {
    				}
    				b_angelokastron = {
    				}
    				b_arta = {
    				}
    				b_agnanta = {
    				}
    				b_thomokastron = {
    				}
    				b_vonitsza = {
    				}
    				b_vlacherna = {
    				}
    				b_rogoi = {
    				}
    			}
    			c_cephalonia = {
    				color={ 146 75 121 }
    				color2={ 255 255 20 }
    				
    				turkish = "Iyonya"
    				
    				b_corfu = {
    				}
    				b_lefkas = {
    					turkish = "Ayamavra"
    				}
    				b_palaiofrourio = {
    				}
    				b_kefalonia = {
    				}
    				b_zante = {
    				}
    				b_paxos = {
    					italian = "Passo"
    					turkish = "Paksa"
    				}
    				b_ithaca = {
    					turkish = "Fiaki"
    				}
    				b_cerigo = {
    					turkish = "Çuha"
    				}
    			}
    		}
    	}
    	
*!IMPORTANT!*

1. A Kingdom is composed of Duchies and Duchies are composed of Counties. Once you  created the kingdom above, you need to go and remove 
d\_dyrrachion{ }  & d\_epirus {} and what is inside from other sections of this file! 
2. The kingdom created below still does not reflect the territories of the Albanian Culture. It leaves out Kosova (Rascia ingame) and other territories. I will deal with them in another version.
3. 

### Dynasties
Open the file _/common/dynasties/00\_dynasties.txt_ and change the following dynasties: 

    15001 = {
    	name="Thopia"
    	culture = albanian
    }
    15002 = {
    	name="Bua Spatas"
    	culture = albanian
    }
    15003 = {
    	name="Muzaka"
    	culture = albanian
    }

    508 = {
    	name="Kastriotis"
    	culture = albanian
    }
    
I am sure there are other Albanian dynasties "mistaken" by Paradox to be other nationalities, please feel free to check the page and let me know, or do a pull request.

## TODOs
* Remove dependency on "The Ruler Designer"
* Add Kosovo and other territories to the Arberia Kingdom.
