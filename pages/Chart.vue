<template>
	<div>
		<section class="hero is-success">
			<div class="hero-body">
				<p class="title">
					<i class="fas fa-hamburger"></i> 음식 가격 변화
					<i class="fas fa-bacon"></i>
				</p>
				<p class="subtile">
					재미로 보는 시대별 물가 변화
				</p>
			</div>
		</section>
		<hr />
		<section class="columns">
			<div class="column">
				<article class="message">
					<div class="message-header">
						가격변동
					</div>
					<div class="message-body">
						<div
							id="lineChart"
							:style="`width:100%;height:${chartHeight}px`"
						></div>
						<div class="content">
							<p class="tag is-danger">출처</p>
							<a href="https://www.kamis.or.kr/customer/price/wholesale/item.do">
								유통정보</a
							>
						</div>
					</div>
				</article>
			</div>
			<div class="column">
				<article class="message">
					<div class="message-header">
						외식 목적
					</div>
					<div class="message-body">
						<div id="pieChart" style="width:100%;height:400px"></div>
						<div class="content">
					
						</div>
					</div>
				</article>
			</div>
		</section>
	</div>
</template>
<script>
    import toastuiChart from '~/plugins/toastuiChart';
    let showChart = false;
    const dogCaringMoney = {
        categories: [
            '2000년',
            '2005년',
            '2010년',
            '2015년',
            '2020년',
        ], // y-axis
        series: [
            // x-axis
            {
                name: '비빔밥(원)',
                data: [2000, 4500, 7000, 8000, 9000],
            }, {
                name: '불고기(원)',
                data: [3000, 4200, 4000, 7000 ,12000],
            }, 
        ],
    };
    const dogStartYear = {
        categories: ['사례 수'],
        series: [{
            name: '집에서 해먹기 귀찮아서',
            data: 40.6,
        }, {
            name: '해먹는것 보다 가격이 싸서',
            data: 12.5,
        }, {
            name: '다양한 음식을 먹기 위해서',
            data: 15.1,
        }, {
            name: '방송에 나온 집이여서',
            data: 4.2,
        }, {
            name: '사람들과 교류를 위해서',
            data: 2.9,
        }, ],
    };
    export default {
        data() {
            return {
                chartHeight: 400
            };
        },
        mounted() {
            if (!showChart && process.client) {
                if (!toastuiChart('bar', 'lineChart', dogCaringMoney)) return;
                if (!toastuiChart('pie', 'pieChart', dogStartYear)) return;
                showChart = true;
            }
        },
        destroyed() {
            showChart = false;
        },
    };
</script>