<template>
    <div id="map"></div>
</template>

<script>
// 40d25d977cfee0e73663ca3c67704f92
import mapAxis from "assets/mapAxis.json";

export default {
    data () { 
        return {};
    },
    mounted() {
        // 카카오 디벨로퍼에서 발급받은 api key
        const API_KEY = "40d25d977cfee0e73663ca3c67704f92"

        if (window.kakao && window.kakao.map) {
            this.initMap();

        } else {
            const script = document.createElement("script");
            script.onload = () => kakao.maps.load(this.initMap);
            script.src = 'http://dapi.kakao.com/v2/maps/sdk.js?autoload=false&appkey=40d25d977cfee0e73663ca3c67704f92';
            document.head.appendChild(script);
        }
    },
    method: {
        initMap() {
            const mapContainer =document.getElementById("map");
            const mapOption = {
                center: new kakao.maps.LatLng(36.73035, 127.967487),
                level: 13,
            };
            const map = new kakao.maps.Map(mapContainer, mapOption);
            const positions = mapAxis.map((position) => (
                {
                    latlng: new kakao.maps.LatLng(...position.latlng),
                    cityName
                }));

                positions.forEach((item)=>{
                    const marker = new kakao.maps.Marker({
                        position: item.latlng,
                    });
                    marker.setMap(map);

                    kakao.maps.event.addListener(marker, "click", ()=>{
                        const res = marker.getPostion();

                        console.log(res);
                    });
                });
        },
    },
};
</script>

<style lang="scss" scoped>
#map{
    width: 400px;
    height: 400px;

    border-radius: 16px;
    box-shadow: 0px 0px 24px 5px rgba(0, 0, 0, 0.1);
    background-color: beige;
}
</style>