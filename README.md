# shopping process coded with bash script
# this project is about cart item selection and checkout after you must have been done shopping

#always use ctrl +d to go to previous menu and eventually exit at last menu
#this project is about cart item selection and checkout after you must have been done shopping
  output= 0
  select name in books drugs cars outputs
  do
   case $name in 
    books)
        select book in Quran ajrumiyyah sarfu_kaafi 
          do
           echo "you want to buy $book"
           if [ $book == "Quran" ]
           then
              output=$((output + 1500))
              echo "Quran price is only 1500, your total checkout price is below"
           elif [ $book == "ajrumiyyah" ]
            then 
              output=$((output + 250))
              echo "ajrumiyyah price is only 250, your total checkout price is below"
           elif [ $book == "sarfu_kaafi" ]
            then 
              output=$((output + 2500)) 
             echo "sarfu_kaafi price is only 2500, your total checkout price is below" 
           else
              echo "incorrect input"
           fi
           echo "your present total is  $output"

          done;;
     drugs)
         select drug in paracetamol vencik panadol 
           do
          echo "you want to buy $drug"
          if [ $drug == "paracetamol" ]
           then
              output=$((output + 200))
              echo "paracetamol price is only 200, your total checkout price is below"
           elif [ $drug == "vencik" ]
            then 
              output=$((output + 220))
              echo "vencik price is only 220, your total checkout price is below"
           elif [ $drug == "panadol" ]
            then 
              output=$((output + 1000))
              echo "panadol price is only 1000, your total checkout price is below"  
           else
              echo "incorrect input"
           fi
           echo "your present total is  $output"
           done;; 
     cars)
       select car in toyota mazda ferari 
         do
         echo "you want to buy $car"
          if [ $car == "toyota" ]
           then
              output=$((output + 4500))
              echo "toyota price is only 4500, your total checkout price is below"
           elif [ $car == "mazda" ]
            then 
              output=$((output + 4000))
              echo "mazda price is only 4000, your total checkout price is below"
           elif [ $car == "ferari" ]
            then 
              output=$((output + 6000))
              echo "ferari price is only 6000, your total checkout price is below"  
           else
              echo "incorrect input"
           fi
           echo "your present total is  $output"        
          done;; 
     outputs)
         echo "your total checkout cost $output";;
     ?)    #catches single non alphabet letter eg special chars 
        echo "you gave me $name";;
     *)   #catches multiple chars/string
          echo "you gave me $name";;
     esac
  done
 

