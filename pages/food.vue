<template>
	<div>
		<section class="hero is-warning">
			<div class="hero-body">
        <p class="title">
          <i class="fas fa-utensils"></i> 전국
          <i class="fas fa-utensils"></i> 불고기 랭킹!
        <p class="subtile">
          맛집 list
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
				<a href="https://www.mangoplate.com/top_lists/613_bulgogi">출처</a><br />
				<p class="tag is-danger">출처</p>
				<a href="https://github.com/jisu7487/w/blob/main/food.json">MY GIT HUB</a><br />
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