- [How to change map tiles](#how-to-change-map-tiles)

## How to change map tiles

Q: How can I change the map files for the live map in SnailyCAD?

A:

1. First you'll need to extract your map files(.ytd) from OpenIV. Make sure they have the correct naming:

   - `minimap_sea_0_0.png`
   - `minimap_sea_0_1.png`
   - `minimap_sea_1_0.png`
   - `minimap_sea_1_1.png`
   - `minimap_sea_2_0.png`
   - `minimap_sea_2_1.png`

2. Navigate to the following folder: `public/tiles/`.
3. Replace the corresponding files with your custom tiles.
4. All done! Restart the CAD and you should see your custom map.

- [How to setup a websocket for SSL](#How-To-Setup-Websocket-with-ssl)

## How to setup a websocket for ssl!

First you need to install the livemap module!

Secondly you'll need to add these to your nginx configuration:

```

location /blips {
    proxy_pass http://FiveMIP:livemap_port/blips;
}


location /ws {
    proxy_pass http://fivemip:livemap_port/;

    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header X-Forwarded-Proto $scheme;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "upgrade";
}
```

then inside of your cad settings under livemap url set this as the websocket: `wss://example.com/ws`
finally it should work!