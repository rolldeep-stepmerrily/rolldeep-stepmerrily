```typescript
const rolldeep: Developer = {
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
      getBirthDate: () => dayjs('2025-04-05'),
    },
  },
  hobby: {
    bass: 'practice hard 🎸',
  },
  lifeStatus: async () => {
    const baby = rolldeep.family.baby;
    const birthDate = baby.getBirthDate();
    const now = dayjs();
    const timeUntilBirth = birthDate.diff(now, 'millisecond');

    const waitForBaby = () =>
      new Promise<string>((resolve) => {
        setTimeout(() => {
          resolve(`${baby.name}이가 태어났어요! 👶`);
        }, Math.max(0, timeUntilBirth));
      });

    return await waitForBaby();
  },
};

export default rolldeep;
```
