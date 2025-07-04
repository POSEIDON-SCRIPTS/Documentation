# config.js

```javascript
TR = {

    LANG: 'EN',

    EN: {
        SAVE: "Save SETTINGS ", 
        HUD_STYLE: "🎮 HUD STYLE",
        COLOR_SETTINGS: "🌈 COLOR",
        HUD: "Choose how your HUD elements will be displayed in the game. ",
        SETTINGS: 'SETT<span style="color: white">INGS</span>',

        BOX: "Box",
        FULLCIRCLE: "Full Circle",
        PARTIALCIRCLE: "Partial Circle", 

    }
}

// Do not change the id of the rows, it will break the script
rows = [
    { name: "HEALTH", tooltip: "Player health bar", id: "health" },
    { name: "STAMINA", tooltip: "Player stamina meter", id: "stamina" },
    { name: "HUNGRY", tooltip: "Hunger level", id: "food" },
    { name: "THIRST", tooltip: "Thirst level", id: "water" },
    { name: "STRESS", tooltip: "Stress indicator" },
    { name: "POOP", tooltip: "Poop level", id: "poop" },
    { name: "PISS", tooltip: "Piss level", id: "piss" },
    { name: "SHOWER", tooltip: "Shower level", id: "shower" },
    { name: "TEMPERATURE", tooltip: "Body temperature", id: "temperature" },
    { name: "ONESYNC", tooltip: "Onesync status", id: "onesync" },
    { name: "HORSE HEALTH", tooltip: "Horse health", id: "horsehealth" },
    { name: "HORSE STAMINA", tooltip: "Horse stamina", id: "horsestamina" },
    { name: "MICROPHONE", tooltip: "Microphone status", id: "microphone" },
    { name: "ALCOHOL", tooltip: "Alcohol level", id: "alcohol" },
    { name: "DEADEYE", tooltip: "Deadeye level", id: "deadeye" },
    { name: "STRESS", tooltip: "Stress level", id: "stress" },
  ];

Config = {
    IconType: 3, // Change this 1, 2, 3

    icons: {
        health: {
            show: true,
            box: {
                text: true,
                icon: 'fa-solid fa-heart',
                mainColor: '#f44336', 
                activeColor: '#ff7961',
                secondColor: '#f44336'
            },
            fullcircle: {
                text: true,
                icon: 'fa-solid fa-heart',
                mainColor: '#f44336',
                secondColor: 'white',
                activeColor: '#ff7961'
            },
            partialcircle: {
                text: true,
                icon: 'fa-solid fa-heart',
                mainColor: '#f44336',
                activeColor: '#ff7961',
                secondColor: '#f44336'
            }
        },

        stamina: {
            show: true,
            box: {
                text: true,
                icon: 'fa-thin fa-person-running',
                mainColor: '#61FF00',
                activeColor: '#9dff57',
                secondColor: '#61FF00'
            },
            fullcircle: {
                text: true,
                icon: 'fa-thin fa-person-running',
                mainColor: '#61FF00',
                secondColor: 'white',
                activeColor: '#9dff57'
            },
            partialcircle: {
                text: true,
                icon: 'fa-thin fa-person-running',
                mainColor: '#61FF00',
                activeColor: '#9dff57',
                secondColor: '#61FF00'
            }
        },
        food: {
            show: true,
            box: {
                text: true,
                icon: 'fa-solid fa-utensils',
                mainColor: '#FFB800',
                activeColor: '#ffd54f',
                secondColor: '#FFB800'
            },
            fullcircle: {
                text: true,
                icon: 'fa-solid fa-utensils',
                mainColor: '#FFB800',
                secondColor: 'white',
                activeColor: '#ffd54f'
            },
            partialcircle: {
                text: true,
                icon: 'fa-solid fa-utensils',
                mainColor: '#FFB800',
                activeColor: '#ffd54f',
                secondColor: '#FFB800'
            }
        },
        water: {
            show: true,
            box: {
                text: true,
                icon: 'fa-solid fa-droplet',
                mainColor: '#0075FF',
                activeColor: '#4dafff',
                secondColor: '#0075FF'
            },
            fullcircle: {
                text: true,
                icon: 'fa-solid fa-droplet',
                mainColor: '#0075FF',
                secondColor: 'white',
                activeColor: '#4dafff'
            },
            partialcircle: {
                text: true,
                icon: 'fa-solid fa-droplet',
                mainColor: '#0075FF',
                activeColor: '#4dafff',
                secondColor: '#0075FF'
            }
        },
        poop: {
            show: true,
            box: {
                text: true,
                icon: 'fa-solid fa-poop',
                mainColor: '#8B4513',
                activeColor: '#a0522d',
                secondColor: '#8B4513'
            },
            fullcircle: {
                text: true,
                icon: 'fa-solid fa-poop',
                mainColor: '#8B4513',
                secondColor: 'white',
                activeColor: '#a0522d'
            },
            partialcircle: {
                text: true,
                icon: 'fa-solid fa-poop',
                mainColor: '#8B4513',
                activeColor: '#a0522d',
                secondColor: '#8B4513'
            }
        },
        piss: {
            show: true,
            box: {
                text: true,
                icon: 'fa-solid fa-toilet',
                mainColor: '#FFD700',
                activeColor: '#ffecb3',
                secondColor: '#FFD700'
            },
            fullcircle: {
                text: true,
                icon: 'fa-solid fa-toilet',
                mainColor: '#FFD700',
                secondColor: 'white',
                activeColor: '#ffecb3'
            },
            partialcircle: {
                text: true,
                icon: 'fa-solid fa-toilet',
                mainColor: '#FFD700',
                activeColor: '#ffecb3',
                secondColor: '#FFD700'
            }
        },
        shower: {
            show: true,
            box: {
                text: true,
                icon: 'fa-solid fa-bath',
                mainColor: '#FFB800',
                activeColor: '#ffd54f',
                secondColor: '#FFB800'
            },
            fullcircle: {
                text: true,
                icon: 'fa-solid fa-bath',
                mainColor: '#FFB800',
                secondColor: 'white',
                activeColor: '#ffd54f'
            },
            partialcircle: {
                text: true,
                icon: 'fa-solid fa-bath',
                mainColor: '#FFB800',
                activeColor: '#ffd54f',
                secondColor: '#FFB800'
            }
        },
        temperature: {
            show: true,
            box: {
                text: true,
                icon: 'fa-solid fa-temperature-full',
                mainColor: '#FF4500',
                activeColor: '#ff7f50',
                secondColor: '#FF4500'
            },
            fullcircle: {
                text: true,
                icon: 'fa-solid fa-temperature-full',
                mainColor: '#FF4500',
                secondColor: 'white',
                activeColor: '#ff7f50'
            },
            partialcircle: {
                text: true,
                icon: 'fa-solid fa-temperature-full',
                mainColor: '#FF4500',
                activeColor: '#ff7f50',
                secondColor: '#FF4500'
            }
        },
        onesync: {
            show: true,
            box: {
                text: true,
                icon: 'fa-solid fa-people',
                mainColor: '#FF5733',
                activeColor: '#ff8a65',
                secondColor: '#FF5733'
            },
            fullcircle: {
                text: true,
                icon: 'fa-solid fa-people',
                mainColor: '#FF5733',
                secondColor: 'white',
                activeColor: '#ff8a65'
            },
            partialcircle: {
                text: true,
                icon: 'fa-solid fa-people',
                mainColor: '#FF5733',
                activeColor: '#ff8a65',
                secondColor: '#FF5733'
            }
        },
        horsehealth: {
            show: true,
            box: {
                text: true,
                icon: 'fa-solid fa-horse',
                mainColor: 'black',
                activeColor: '#696969',
                secondColor: 'black'
            },
            fullcircle: {
                text: true,
                icon: 'fa-solid fa-horse',
                mainColor: 'black',
                secondColor: 'white',
                activeColor: '#696969'
            },
            partialcircle: {
                text: true,
                icon: 'fa-solid fa-horse',
                mainColor: 'black',
                activeColor: '#696969',
                secondColor: 'black'
            }
        },
        horsestamina: {
            show: true,
            box: {
                text: true,
                icon: 'fa-solid fa-magnet',
                mainColor: 'gray',
                activeColor: '#b0b0b0',
                secondColor: 'gray'
            },
            fullcircle: {
                text: true,
                icon: 'fa-solid fa-magnet',
                mainColor: 'gray',
                secondColor: 'white',
                activeColor: '#b0b0b0'
            },
            partialcircle: {
                text: true,
                icon: 'fa-solid fa-magnet',
                mainColor: 'gray',
                activeColor: '#b0b0b0',
                secondColor: 'gray'
            }
        },
        microphone: {
            show: true,
            box: {
                text: true,
                icon: 'fa-solid fa-microphone',
                mainColor: 'black',
                activeColor: 'red',
                secondColor: 'black'
            },
            fullcircle: {
                text: true,
                icon: 'fa-solid fa-microphone',
                mainColor: 'black',
                secondColor: 'white',
                activeColor: 'red'
            },
            partialcircle: {
                text: true,
                icon: 'fa-solid fa-microphone',
                mainColor: 'red',
                activeColor: 'green',
                secondColor: 'red'
            }
        },
        alcohol: {
            show: true,
            box: {
                text: true,
                icon: 'fa-solid fa-wine-bottle',
                mainColor: '#8B0000', // Dark Red (Wine)
                activeColor: '#FFD700', // Gold (Whiskey/Champagne)
                secondColor: '#8B0000' // Brown (Brandy/Rum)
            },
            fullcircle: {
                text: true,
                icon: 'fa-solid fa-wine-bottle',
                mainColor: '#6A0DAD', // Purple (Grape Wine)
                secondColor: '#F5F5DC', // Beige (Champagne)
                activeColor: '#6A0DAD' // Chocolate (Rum/Bourbon)
            },
            partialcircle: {
                text: true,
                icon: 'fa-solid fa-wine-bottle',
                mainColor: '#800000', // Maroon (Red Wine)
                activeColor: '#228B22', // Forest Green (Absinthe)
                secondColor: '#800000' // Silver (Vodka/Gin)
            }
        },

        deadeye: {
            show: true,
            box: {
                text: true,
                icon: 'fa-solid fa-eye',
                mainColor: '#8B0000', // Dark Red (Wine)
                activeColor: '#FFD700', // Gold (Whiskey/Champagne)
                secondColor: '#8B0000' // Brown (Brandy/Rum)
            },
            fullcircle: {
                text: true,
                icon: 'fa-solid fa-eye',
                mainColor: '#6A0DAD', // Purple (Grape Wine)
                secondColor: '#F5F5DC', // Beige (Champagne)
                activeColor: '#6A0DAD' // Chocolate (Rum/Bourbon)
            },
            partialcircle: {
                text: true,
                icon: 'fa-solid fa-eye',
                mainColor: '#800000', // Maroon (Red Wine)
                activeColor: '#228B22', // Forest Green (Absinthe)
                secondColor: '#800000' // Silver (Vodka/Gin)
            }
        },
        stress: {
            show: true,
            box: {
                text: true,
                icon: 'fa-solid fa-brain',
                mainColor: '#FF5733',
                activeColor: '#ff8a65',
                secondColor: '#FF5733'
            },
            fullcircle: {
                text: true,
                icon: 'fa-solid fa-brain',
                mainColor: '#FF5733',
                secondColor: 'white',
                activeColor: '#ff8a65'
            },
            partialcircle: {
                text: true,
                icon: 'fa-solid fa-brain',
                mainColor: '#FF5733',
                activeColor: '#ff8a65',
                secondColor: '#FF5733'
            }
        }
        
    }
};

```
