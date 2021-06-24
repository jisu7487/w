<template>
	<div>
		<section class="hero is-warning">
			<div class="hero-body">
				<p class="title"><i class="ffas fa-utensils">
                    </i>대전의 맛집 정보</p>
				<p class="subtile">
					맛집을 평가해줍니다
				</p>
			</div>
		</section>
		<hr />
		<section class="columns"></section>
		<div class="column">
			<table class="table">
				<thead>
					<th>가게이름</th>
					<th>대표메뉴 / 가격</th>
                    <th>위치</th>
				</thead>
				<tbody>
					<template v-for="pos in tablefoodKey.length">
						<tr :key="pos">
							<td>{{ tableName[pos - 1]}}</td>
                            <td>{{ tableContent[pos - 1]}}</td>
                            <td>{{ tableTag[pos - 1]}}</td>						
						</tr>
					</template>
				</tbody>
			</table>
            <div class="content">
				<p class="tag is-danger">출처</p>
				<a href="https://github.com/jisu7487/5.26">MY GIT HUB</a><br />
			</div>
		</div>
		<div class="column"></div>
	</div>
</template>
<script>
	import axios from 'axios';
	export default {
		async asyncData() {
			const food = await axios.get('https://raw.githubusercontent.com/jisu7487/w/main/food.json');
            //alert(Object.keys(food));
            console.log(Object.keys(food.data.message));
			return {
				tableName: food.data.message,
                tablefoodKey: Object.keys(food.data.message),
                tableContent: food.data.content,
                tableTag: food.data.tag
                
                
			};
		}
	};
</script>