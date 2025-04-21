```typescript
export const rolldeep: Developer & Daddy = {
  dev: {
    coding: 'with my not smart 🧠',
    favorite: {
      language: 'TypeScript',
      framework: 'NestJS',
      orm: 'Prisma',
    },
  },
  family: {
    wife: '❤️'.repeat(Number.MAX_SAFE_INTEGER),
    baby: {
      name: '이현',
      gender: EGender.MALE,
      isBorn: true,
      getBirthDate: () => dayjs('2025-04-04'),
    },
  },
  hobby: {
    bass: 'practicing diligently 🎸',
  },
  lifeStatus: async () => {
    const { baby } = rolldeep.family;
    const birthDate = baby.getBirthDate();
    const now = dayjs();
    const babyAge = now.diff(birthDate, 'day');

    const parentingActivities = [
      '분유 먹이기 🍼',
      '기저귀 갈기 👶',
      '재우기 😴',
      '놀아주기 🎮',
      '목욕시키기 🛁',
      '뽀뽀해주기 💋',
      '안아주기 🤗',
    ];

    const parenting = () => {
      return new Promise<string>((resolve) => {
        console.log(`${baby.name}이(${babyAge}일차) 육아 시작!`);
        let activityIndex = 0;
        const activityInterval = setInterval(() => {
          const currentActivity = parentingActivities[activityIndex];

          console.log(`현재 육아 활동: ${currentActivity}`);

          activityIndex = (activityIndex + 1) % parentingActivities.length;
        }, 2000);

        setTimeout(() => {
          clearInterval(activityInterval);

          console.log(`${baby.name}이가 잠들었습니다...`);

          resolve('3시간 동안 쉬는 시간!');
        }, 10800000); // 3 hours
      });
    };

    return await parenting();
  },
};
```
