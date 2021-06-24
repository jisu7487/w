<template>
    <div>
        <section class = "hero is-link" style="text-align: center;">
            <div class="hero-body">
                <p class="title"><i class="fas fa-receipt"></i> 집에서먹는 한식!</p>
                <p class ="subtitle">비빔밥 레시피를 알려드립니다.</p>
            </div>
        </section>
        <hr/>
        <section class = "columns" >
            <div style="width: 15%;"></div>
            <div class="column" >
                <article class="message" style="text-align: center;">
                    <div class="message-header">메뉴를 선택해 주세요.</div>
                    <div class="message-body">
                        <table class = "table is-striped is-hoverable is-fullwidth">
                            <thead>
                                <tr>
                                    <th></th>
                                    <th></th>
                                </tr>
                            </thead>
                            <tbody>
                                <template v-for="pos in content.length">
                                    <tr :key="pos">
                                        <td style="width: 7cm;"><img v-bind:src = photo[pos-1]></td>
                                        <td><a v-bind:href = 'link[pos -1]'>{{content[pos-1]}}</a></td>
                                    </tr>
                                </template>
                               </tbody>
                        </table>
                    </div>
                </article>
                
                <div class="content">
                   <span class="tag is-danger">출처</span> <a href="https://www.10000recipe.com/index.html">만개의 레시피</a>
                </div>
                <div class="content">
                    <span class="tag is-warning">JSON</span>
                    <a href="/photo.json">Photo</a>
                </div>
            </div>
            <div style="width: 15%;"></div>
        </section>

    </div>
</template>
<script>
    import photojson from "~/static/photo.json";
    export default {
        data() {
			return {
                photo: photojson.images,
                content: photojson.names,
                link: photojson.link
			};
        }
    };
</script>