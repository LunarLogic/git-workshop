           __  ___             _            ____
          /  |/  /__ _______ _(_)__ ___ _  |_  /
         / /|_/ / -_) __/ _ `/ / _ \ _ `/ _/_ <
        /_/  /_/\__/_/  \_, /_/_//_\_, / /____/
                       /___/      /___/
        • back merging:
        • gco -b oklahoma
        • echo "a day in oklahoma" >> diary
        • git commit -am "oklahoma 1"
        • gco master
        • git merge oklahoma
        • uups CONFLICTS, lets back out
        • git merge --abort
        • gco oklahoma
        • git merge master
        • resolve conflicts
        • git add; git commit
        • gco master
        • git merge oklahoma
        • nice and easy merge

















































































slide 014
