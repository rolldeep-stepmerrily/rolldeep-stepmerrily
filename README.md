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
      name: '☀️햇살',
      gender: EGender.MALE,
      isBorn: false,
      getBirthDate: () => dayjs('2025-04-05'),
    },
  },
  hobby: {
    bass: 'practicing diligently 🎸',
  },
  lifeStatus: async () => {
    const { baby } = rolldeep.family;
    const birthDate = baby.getBirthDate();
    const now = dayjs();
    const timeUntilBirth = birthDate.diff(now, 'millisecond');

    const messages: readonly string[] = [
      `${baby.name}아 하루 빨리 보고싶다 🥰`,
      '건강하게 잘 자라고 있지? 😊',
      '엄마랑 사이좋게 지내고 있어 💞',
      '아빠가 든든하게 지켜줄게 💪',
    ];

    const waitForBaby = () => {
      return new Promise<string>((resolve) => {
        let messageIndex = 0;
        const messageInterval = setInterval(() => {
          console.log(messages[messageIndex]);

          messageIndex = (messageIndex + 1) % messages.length;
        }, 2000);

        setTimeout(
          () => {
            baby.isBorn = true;
            clearInterval(messageInterval);
            resolve(`${baby.name}이가 태어났어요! 👶`);
          },
          Math.max(0, timeUntilBirth),
        );
      });
    };

    return await waitForBaby();
  },
};
```
