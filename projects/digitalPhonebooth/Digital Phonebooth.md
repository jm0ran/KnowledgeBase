In my Senior Year at Platt Technical Highschool I joined a team of three to compete in Skills USA 2022 in the chapter display category. One of the group members approached me in class one day and asked if I would be able to make an iPad app that played an audio clip for a project he was planning. I told him that it would be no problem and he began to show me his idea for the project in question and I realized that I could make a lot more than an mp3 player.

The task was to build a physical display to represent that years theme of "United as One". Our group decided to construct a phone booth to represent a connection point for people all over the world. My role was to handle the interactive portions of the project. The idea went from a simple mp3 player, to a app with a virtual dialing system, and finally to modifying an actual rotary phone to control the display. I got my hands on an old rotary phone buried in a school closet and started going to work on figuring out just how I would go about the modification.

This was the first project I had ever used GPIO or any physical output for the computer so the first few days were focused on discovery. I found the leads I needed and learned that the rotary dial was essentially just one large switch which opened once for every number it turned through. Knowing that I connected the phone to a Raspberry PI and started to code.

The code portion for interpreting the dial was pretty simple. I wrote it in Python utilizing the GPIO and time libraries. It was all about timing and while it took a lot of tweaking, I eventually got the timing just right and was getting consistent results when dialing a digit. The next step would be getting the information from the Raspberry Pi (which would be embedded in the phone) to the tablet running the visual and audio component.

To send the signal I leveraged the USB C port on the Raspberry PI 4 to emulate a USB device, specifically a keyboard. I was able to impersonate a keyboard and send keystrokes that correlated to the dialed number essentially turning the rotary phone into a giant numpad.

Now that I had a way to get input from the phone, I moved onto the next portion of the project. For the visual and audio component I created a UI in Unity that would move across a map to play audio clips from different people across the world. The programming mainly consisted of making smooth transitions between spots on the map and bringing UI elements in and out of the view depending on what state the program was in.

When I was younger I was fortunate enough to live in Singapore for three years as my mother has signed a contact to teach in an international school. I met a lot of kids like me who had come from all different parts of the world while their parents worked in the country for a few years. Even after leaving almost 7 years ago I still have contact with many of them which put me in a unique position to source genuine clips from people who were living all over the world.

The final step was playing the audio clip through the phone's handset and while this seemed daunting at first, it ended up just being a case of soldering a salvaged 3.5mm audio cable to the handsets connections. With sound working, the initial version of the converted rotary phone was complete.

Our first competition was at the state level, the phone booth was built out of an old server rack and I mounted the phone inside. The tablet was mounted above to display the map and what the user had dialed. It wasn't easy to transport, but with a pickup truck and some manpower we got it to the competition in one piece. We won the state level competition and preparations began for nationals.

![[phoneBoothv1.jpg|400]]

While we loved the idea of repurposing a server rack for our phone both, reality stepped in when we realized we would have to transport the piece to Georgia on a plane. We started from scratch and began to rebuild the phone booth in a way that would let us flat pack it for transport. 

On top of changes to the booth itself, I made various improvements to the interactable portion of the project. We acquired a wall mounted phone to fit the theme better, I connected the hang up functionality to reset dial input and end a call preemptively, and I added a slide show to each audio clip to provide some visual context.

![[phonev2_1.jpg|300]]
![[phonev2_2.jpg|300]]
![[phonev2_3.jpg|500]]
![[phoneBoothv2.jpg||400]]

While we didn't end up on the podium, we had the opportunity to show our project off to a large number of people. It was incredibly satisfying when someone stepped in and realized that the phone wasn't just there for decoration and that it had been functionally implemented. 

This project was a strange one because for the most part the category was for hands on trades where you would build something physical. When I joined the group initially there wasn't much of a role I'd play but that vagueness pushed me out of my comfort zone. There was a lot of firsts in this projects for me from painting, soldering, and some light carpentry on top of the programming I learned a lot. Building this phone booth encouraged me to apply my skills in new and unique ways and I am incredibly proud of how it turned out.