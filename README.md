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
  lifeStatus: async () => {},
};
```
